# SOC2: The Screenshots Will Continue Until Security Improves

A practical guide to SOC2 compliance from someone who actually project-managed it, covering what it is, when to pursue it, what it really involves, and how to navigate the process without letting it derail your company.

## The Bottom Line for Customers

**SOC2 is a weak positive indicator of security maturity**, in the same ballpark of significance as a penetration test report (but less significant than multiple pentest reports).

**Key distinctions:**
- **SOC2 is an accounting-style, or "real", audit.** It confirms on-paper claims companies make about their security processes. It's nothing like "security audits" or "penetration tests", which are heavily adversarial, engineering-driven, and involve giving third parties free rein to find interesting problems.
- **SOC2 is about the security of the company, not the company's products.** A SOC2 audit would tell you something about whether the customer support team could pop a shell on production machines; it wouldn't tell you anything about whether an attacker could pop a shell with a SQL Injection vulnerability.
- **The guts of a SOC2 audit are a giant spreadsheet questionnaire (the "DRL") and a battery of screenshots** serving as evidence for the answers in the questionnaire.
- **The SOC2 DRL is high-level and abstract**, the product of accounting industry standards like the COSO framework; it understands things like "git" and "multi-factor authentication", but nothing lower-level than that.
- **There are two kinds of SOC2 reports:** The "Type I", which takes a point-in-time snapshot of a company's processes, and the "Type II", which confirms over several months that the company consistently adhered to those processes. You can't "flunk" a Type I audit. But it's more annoying to pass a Type II, because you can't travel back in time to close a gap you had last year.

**What SOC2 does assure that pentests don't:**
- Consistent policies for who in the company gets access to what
- That everyone in the company has to log in with 2FA
- The capability, at least, to fire alerts when weird things show up in logs
- Severed employees reliably have their access terminated
- That the company is not actually run by 4 raccoons in a trenchcoat (or, if it is, that suitable policy has been written documenting and accepting the risk)

**Depending on the kind of company you're looking at:** Intensely technical company? High-risk engineering? Look for the pentest. Huge number of employees? Get the SOC2 report.

## What's SOC2?

SOC2 is the best-known infosec certification, and the only one routinely demanded by customers.

**The structure:** There's a structure to the things you claim in SOC2, the AICPA's "Trust Services Criteria" and something called "the COSO framework". These are broken down into categories: security, availability, transaction integrity, confidentiality, and privacy. "Security" is mandatory, and is the only one that matters for most companies.

**"DRL" is "Document Request List"**

**The ground truth of SOC2** is something called the DRL, which is a giant spreadsheet that your auditor customizes to your company after a scoping call. You can try to reason back every line item on the DRL to first accounting principles, but that'd be approximately as productive as trying to reason about contract law from first principles after paying a lawyer to review an agreement. Just take their word for it.

**With me so far? SOC2. It's a big spreadsheet an accounting firm gives you to fill out.**

## When Should You SOC2?

**We waited as long as we felt we could.**

**Important distinction:** "Getting SOC2-certified" isn't the same as "doing the engineering work to get SOC2-certified". **Do the engineering now. As early as you can.** The work, and particularly its up-front costs, scale with the size of your team.

**The audit itself though doesn't matter**, except to answer the customer request "can I have your SOC2 report?"

**So, "when should I SOC2?"** Do it when it's more economical to suck it up and get the certification than it is to individually hand-hold customer prospects through your security process.

**Why customers ask for SOC2:** It's viral, like the GPL. The DRL strongly suggests you have a policy to "collect SOC2 reports from all your vendors". Some SOC2 product vendors offer automated security questionnaires for companies to fill out, and they ask for SOC2 reports as well. Your customers ask because they themselves are SOC2, and the AICPA wants them to force you to join the coven.

**That doesn't mean you have to actually do it.** If you can speak confidently about your security practice, you can probably get through anybody's VendorSec process without a SOC2 report. Or you can pay an audit firm to make that problem go away.

**It makes very little sense to get SOC2-certified before your customers demand it.** You can get a long way without certification. If it helps, remember that you can probably make a big purchase order from that Fortune 500 customer contingent on getting your Type I in the next year.

## What SOC2 Made Us Do

Fly.io started preparing for SOC2 more than a year before engaging an auditor, following the playbook from the "Starting 7" blog post. Here's what they implemented:

### Single Sign-On

Every newly-minted CSO has told them that SSO was one of the first 3 things they got worked out when they took the position. Put compliance aside, and it's just obvious why you want a single place to control credentials (forcing phishing-proof MFA, for instance), access to applications, and offboarding. They moved everything they could to Google SSO.

**Inside their network**, they also use a certificate-based SSH access control system (Teleport). To reach Teleport, you need to be on their VPN; to get to their VPN, you need Google SSO. Teleport, however, is authenticated separately, via Github's SSO. So, for SSH, they have two authentication sources of truth, both of which need to work to grant access.

**Teleport's killer feature:** Transcript-level audit logs for every SSH session; with the right privilege level, you can watch other team members sessions, and you can go back in time and see what everyone did. This has the knock-on benefit of providing a transcript-level log of any REPL anyone has to drop into in prod.

**The "SSO tax":** There is, infamously, an "SSO tax" that companies pay to get access to the kinds of SAAS accounts that support SAML or OIDC. It's definitely a pain. If it's early days for your company, for SAAS vendors that don't deal in sensitive information, you can skip the SSO and just restrict who you give access to for the app. But mostly, you should just suck it up and pay for the account that does SSO.

### Protected Branches

They were surprised by how important this was to their auditors. If they had one clearly articulable concern about what might go wrong with their dev process, it was that some developer on their team might "go rogue" and install malware in their hypervisor build.

**It's easy to enable protected branches in Github.** But all that does is make it hard for people to push commits directly to main, which people shouldn't be doing anyways. To get the merit badge, they also had to document an approval process that ensured changes that hit production were reviewed by another developer.

**This wasn't something they were doing prior to SOC2.** They have components that are effectively teams-of-one; getting reviews prior to merging changes for those components would be a drag. But their auditors cared a lot about unsupervised PRs hitting production.

**Their solution:** Post-facto reviews. They do regular reviews on large components, like the Rust fly-proxy that powers their Anycast network and the Go flyd that drives Fly machines. But smaller projects like their private DNS server, and out-of-process changes like urgent bug fixes, can get merged unreviewed (by a subset of authorized developers). They run a Github bot that flags these PRs automatically and hold a weekly meeting where they review the PRs.

### Centralized Logging

A big chunk of the SOC2 DRL is about monitoring systems for problems. Your auditors will gently nudge you towards centralizing this monitoring, but you'll want to do that anyways, because every logging system you have is one you'll have to document, screenshot, and write policy about.

**They got off easy here**, because logging is a feature of their platform; they run very large ElasticSearch and VictoriaMetrics clusters, fed from Vector and Telegraf, and they're generally a single ElasticSearch query away from any event happening anywhere in their infrastructure.

**One thing SOC2 did force them to do was pick a ticketing system**, which is something they'd done their best to avoid for several years. They send alerts to Slack channels and PagerDuty, and then have documented processes for ticketing them.

**HelpScout surprise:** Another thing that surprised them was how much SOC2 mileage they got out of HelpScout. HelpScout is where their support mails (and security@ mails) go to, and while they're not a HelpScout superfan, it is a perfectly cromulent system of record for a bunch of different kinds of events SOC2 cares about, like internal and external reports of security concerns.

### CloudTrail

They barely use anything in AWS other than storage. They compete with AWS! They run their own hardware! But SOC2 audit firms have spent the last 10 years certifying AWS-backed SAAS companies, and have added a whole bunch of AWS-specific line-items to their DRLs. They're now much better at indexing and alerting on CloudTrail than they were before they did SOC2. It's too bad that's not more useful to their security practice.

### Infrastructure-as-Code

Your auditor will probably know what Terraform and CloudFormation are, and they will want you to be using it. Your job will be documenting how your own deployment system (the bring-up for new machines in your environment) is similar to Terraform. Sure, whatever.

**Host inventory annoyance:** An annoyance they did not see coming from previous experience was host inventory. Inventory is trivial if you're an AWS company, because AWS gives you an API and a CLI tool to dump it. They run their own hardware, and while they have several different systems of record for their fleet of machines, they're idiosyncratic and don't document well; they ended up taking screenshots of SQL queries, which wasn't as smooth as just taking a screenshot of their Tailscale ACLs or Google SSO settings.

### MDM and Endpoint Management

**Surprise:** In the year of our lord 2022, doing endpoint security in your SOC2 has fallen out of fashion. They were all geared up to document their endpoint strategy, but it turned out they didn't have to.

You can probably cross this off your checklist of big projects you'll need to get done simply to get a SOC2 certification. You should do the work anyways, on its own merits.

### Boring Company Stuff

**They had three "boring company stuff" surprises:**

**First:** They needed a formal org chart posted where employees could find it. They're not a "titles and management" kind of company (they're tiny), so this was a bother. But, whatever, now they have an org chart.

**Next:** Their auditors wanted to see evidence of annual performance reviews. They don't do annual performance reviews (they're a continuous feedback, routine scheduled 1-on-1 culture). But if you're not doing annual performance reviews, the AICPA can't give assurances that an employee who exfiltrated their production database to Pastebin would be terminated. So now they have pro-forma annual reviews.

This kind of SOC2 thing falls under the category of "things you need to carefully explain to your team so they don't think you've suddenly decided to start stack ranking everyone".

**Finally, background checks:**

Background checks are performative and intrusive. Ask around for horror stories about how they flag candidates for not being able to source the right high school transcripts. Also, for them, they're occasionally illegal: they have employees around the world, including several in European jurisdictions that won't allow them to background check.

This is the only issue they ended up having to seriously back-and-forth with their auditors about. They held the line on refusing to do background checks, and ultimately got out of it after tracking down another company their auditors had worked with, finding out what they did instead of background checks, stealing their process, and telling their auditors "do what you did for them". This worked fine.

### Policies

You're going to write a bunch of policies. It's up to you how seriously you're going to take this. Most companies phone this in and just Google [${POLICY} template], and adopt something from the first search engine result page.

**They wrote their own.** This part of the process was drastically simplified by the work Ryan McGeehan has published, for free, on his "Starting Up Security" site. They have, for instance, an Information Security Policy. It's all in their own words (and theirs quotes grugq). But it's based almost heading-for-heading on Ryan's startup policy, which is brilliant.

**One thing about writing policies inspired by Ryan's examples** is that it liberates you to write things that make sense and read clearly and don't contain the words "whereas" or "designee".

**What they ended up writing:**
1. An Information Security Policy, which everyone on their team has to sign
2. A Data Classification Policy that spells out how to decide which things can go in Slack or Email and which things you have to talk to management before transmitting at all
3. A Document Retention policy (OK, this one they just sourced directly from their lawyers)
4. A Change Management policy
5. A Risk Assessment policy, which says that sometime this year they will build a Risk Assessment spreadsheet explaining how they'll handle a zombie apocalypse (you think they're joking)
6. A Vulnerability Management policy that roughly explains how to run nmap
7. An Access Request policy that tells people which Slack channel to join to ask for access to stuff
8. A Vendor Management policy that propagates the SOC2 virus to all their vendors
9. An Incident Response policy, which they cribbed from Ryan
10. A Business Continuity plan that says that Jerome is in charge if Kurt is ever arrested for robbing a bank
11. An employee handbook

**Slab verification feature:** They use Slab as their company wiki / intranet. Slab surprised them midway through the audit with a feature for "verifying" pages, which might be the highest ROI feature/effort ratio they've come across: they click a button and Slab adds a green banner to a page saying that it's "verified" for the next several months. That's it, that's the feature. Several DRL line items are about "recertifying" policies annually, and this gave them the screenshots they needed for that.

## What We Didn't Let SOC2 Make Us Do

Ordered from most to least surprising (that is, there was no way they were going to do the stuff at the bottom of the list):

1. **Install endpoint software.** See above.
2. **Run a vulnerability scanner.** Their attack surface is overwhelmingly comprised of software they wrote themselves, and they're not cool enough yet to have Nessus checks for their code. They took a note from CloudFlare and, for compliance-driven scanning, just automated nmap.
3. **Actually collect SOC2 reports from all of their vendors**, or document why they didn't. They'll have to get that done soon-ish, but it wasn't a blocker for the certification.
4. **Clear any of the random Prototype Injection vulnerability alerts Dependabot generates** for any project they have that uses Javascript.
5. **Install any agent software on any server anywhere.** They're terrified of agents. Also: of work. The work they allowed themselves to do for SOC2 was, uh, carefully curated. Software to generate extra line items for them to remediate? Not helpful for their process.
6. **Run antivirus on their servers.** They did have to explain why that didn't make any sense, but it boiled down to documenting their deployment and CI/CD systems.
7. **Run any other kind of security product**, be it IDS or WAF or SEM or DAST or ASM or XDR or CASB or anything with "mesh" in the name.

## The Audit Itself

If you talk to people who've done SOC2 before, you'll hear a lot of joking about screenshots. **They're not joking.**

**The whole SOC2 audit is essentially a series of screenshots.** This is jarring to people who have had "security audits" done by consulting firms, in which teams of technical experts jump into your codebase and try to outguess your developers and uncover flaws in their reasoning. Nothing like that happens in a SOC2 audit, because a SOC2 audit is an actual audit.

**Instead, DRL line items are going to ask for evidence** supporting claims you make, like "our production repositories on Github have protected branches enabled so that random people can't commit directly to `main`". That evidence will almost always take the form of one or more screenshots of some management interface with some feature enabled.

**And that's basically it?** They divided the evidence collection stage of the audit up into a series of calls over the course of a week, each of which ate maybe twenty minutes of their time, most of which was them sharing a screen and saying "that checkbox over there, you should screenshot that". They were keyed up for this before the calls started, prepared to be on their A-game for navigating tricky calls, and, nope, it was about as chill a process as you could imagine.

## So, We're Secure Now, And You Could Be Too

**The most important thing:** Keep your goals modest. They've confirmed this over and over again with friends at other companies: **the claims you make in your Type I will bind on your Type II; claims you don't make in your Type I won't.** It stands to reason then that one of your Type I goals should be helping your future self clear a Type II.

**About report quality:** They were a little concerned going into this that the quality of their SOC2 report (and their claims) would be an important factor for customers. And, maybe it will be. They got good auditors! They like them a lot! It wasn't a paint-by-numbers exercise! But in talking to a couple dozen security people at other companies, their takeaway is that **for the most part, having the SOC2 report is what matters, not so much what the SOC2 report says.**

**The five Type I reports trick:** At least one peer, at a highly clueful, highly security-sensitive firm, described to them a vendor that had given them not one, not two, but five consecutive Type I reports. It is possible to synthesize excited bromide in an argon matrix! You can skip all the real work in SOC2! (They've spent the last several weeks trying to convince their CEO that they're not going to do this.)

## What SOC2 Misses

They do a lot of security work that SOC2 doesn't care about; in fact, SOC2 misses most of their security model. They build software in memory-safe languages, work to minimize trust between components, try to find simple access control models that are easy to reason about, and then get their code pentested by professionals.

SOC2 doesn't do a good job of communicating any of that stuff. And that's fine; it doesn't have to. They can write their own security report to explain what they do and how their security practice is structured, which is something they think more companies should do; they'd rather read one of those than a SOC2 report.

**And for all their cynicism, SOC2 dragged them into some process improvements** that they're glad they've got nailed down. It helped to have clueful auditors, and a clear eye about what they were trying to accomplish with the process, if you get their drift.

They expected "entire new cloud provider" to be a complicated case for SOC2 audits. But the whole thing went pretty smoothly (and the un-smooth parts would have hit them no matter what they were building). **If it was easy for them, it'll probably be easier for you. Just don't do it until you have to.**

---

**Source:** [SOC2: The Screenshots Will Continue Until Security Improves](https://fly.io/blog/soc2-the-screenshots-will-continue-until-security-improves/) by Thomas Ptacek, Fly.io Blog, July 7, 2022

