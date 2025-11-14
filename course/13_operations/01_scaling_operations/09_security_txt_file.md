# Does Your Organization Have a Security.txt File?

A proposed Internet standard that helps organizations describe their vulnerability disclosure practices and preferences, making it easier for security researchers to report issues and for organizations to respond to active threats.

## The Problem

**It happens all the time:** Organizations get hacked because there isn't an obvious way for security researchers to let them know about security vulnerabilities or data leaks. Or maybe it isn't entirely clear who should get the report when remote access to an organization's internal network is being sold in the cybercrime underground.

**Real-world example:** A major clothing retailer had VPN credentials stolen by malware and made available to cybercriminals. Finding no security.txt file at the retailer's site, an alert was sent to its "security@" email address. The message was returned with a note saying the email had been blocked. A message was also sent to the retailer's CIO (the only C-level person in the immediate LinkedIn network) — but there was no way to know if anyone had read it.

## What is Security.txt?

In a bid to minimize these scenarios, a growing number of major companies are adopting **"Security.txt,"** a proposed new Internet standard that helps organizations describe their vulnerability disclosure practices and preferences.

**The idea is straightforward:** The organization places a file called `security.txt` in a predictable place — such as `example.com/security.txt`, or `example.com/.well-known/security.txt`.

**What's in the file varies somewhat, but most include:**
- Links to information about the entity's vulnerability disclosure policies
- A contact email address
- Links to bug bounty programs (if applicable)
- Public encryption keys
- Links to thank researchers who have reported important cybersecurity issues
- Links to information about IT security job openings at the company

## Examples

**USAA's security.txt file includes:**
- Links to its bug bounty program
- An email address for disclosing security related matters
- Its public encryption key and vulnerability disclosure policy
- A link to a page where USAA thanks researchers who have reported important cybersecurity issues

**HCA Healthcare's security.txt file is less verbose:**
- Lists a contact email address
- A link to HCA's "responsible disclosure" policies
- A link to information about IT security job openings at the company

## Why It Matters

### Responding to Active Threats

Having a security.txt file can make it easier for organizations to respond to active security threats. When security researchers, journalists, or even malicious hackers need to contact an organization about a security issue, they have a clear, predictable way to do so.

### The Ransomware Angle

**Alex Holden**, founder of the Milwaukee-based consulting firm Hold Security, noted that it's not uncommon for malicious hackers to experience problems getting the attention of the proper people within the very same organization they have just hacked.

"In cases of ransom, the bad guys try to contact the company with their demands," Holden said. "You have no idea how often their messages get caught in filters, get deleted, blocked or ignored."

Having a predictable place to find security contact information helps ensure these messages reach the right people.

### Unofficial vs. Official

Many organizations have long unofficially used (if not advertised) the email address `security@[companydomain]` to accept reports about security incidents or vulnerabilities. However, this isn't standardized, may not be well-publicized, and can be blocked or ignored.

Security.txt provides a standardized, predictable way to find this information.

## Adoption

Although security.txt is not yet an official Internet standard as approved by the **Internet Engineering Task Force (IETF)**, its basic principles have so far been adopted by at least **eight percent of the Fortune 100 companies**.

According to a review of the domain names for the latest Fortune 100 firms, those include:
- Alphabet
- Amazon
- Facebook
- HCA Healthcare
- Kroger
- Procter & Gamble
- USAA
- Walmart

## The Downsides: Getting Deluged

**So if security.txt is so great, why haven't more organizations adopted it yet?**

Setting up a security.txt file tends to invite a rather high volume of spam. Most of these junk emails come from self-appointed penetration testers who — without any invitation to do so — run automated vulnerability discovery tools and then submit the resulting reports in hopes of securing a consulting engagement or a bug bounty fee.

This dynamic was a major topic of discussion in Hacker News threads on security.txt, wherein a number of readers related their experience of being so flooded with low-quality vulnerability scan reports that it became difficult to spot the reports truly worth pursuing further.

**Edwin "EdOverflow" Foudil**, the co-author of the proposed notification standard, acknowledged that junk reports are a major downside for organizations that offer up a security.txt file.

"This is actually stated in the specification itself, and it's incredibly important to highlight that organizations that implement this are going to get flooded," Foudil told KrebsOnSecurity. "One reason bug bounty programs succeed is that they are basically a glorified spam filter. But regardless of what approach you use, you're going to get inundated with these crappy, sub-par reports."

### Managing the Noise

Often these sub-par vulnerability reports come from individuals who have scanned the entire Internet for one or two security vulnerabilities, and then attempted to contact all vulnerable organizations at once in some semi-automated fashion.

**Foudil noted** that many of these nuisance reports can be ignored or grouped by creating filters that look for messages containing keywords commonly found in automated vulnerability scans.

## Success Stories

Despite the spam challenges, Foudil said he's heard tremendous feedback from a number of universities that have implemented security.txt.

"It's been an incredible success with universities, which tend to have lots of older, legacy systems," he said. "In that context, we've seen a ton of valuable reports."

## The Standard's Origin

Foudil says he's delighted that eight of the Fortune 100 firms have already implemented security.txt, even though it has not yet been approved as an IETF standard. When and if security.txt is approved, he hopes to spend more time promoting its benefits.

"I'm not trying to make money off this thing, which came about after chatting with quite a few people at DEFCON [the annual security conference in Las Vegas] who were struggling to report security issues to vendors," Foudil said. "The main reason I don't go out of my way to promote it now is because it's not yet an official standard."

## Key Takeaways

1. **Security.txt provides a standardized way** for organizations to publish their vulnerability disclosure practices and contact information.

2. **It solves a real problem:** Organizations often lack clear, predictable ways for security researchers to report vulnerabilities, which can lead to security issues going unreported or unreported in a timely manner.

3. **There are trade-offs:** While security.txt makes it easier for legitimate researchers to report issues, it also tends to generate a high volume of low-quality, spam-like vulnerability reports.

4. **Spam can be managed:** Organizations can use email filters and keyword-based filtering to manage the noise from automated vulnerability scans.

5. **It's particularly valuable for organizations with legacy systems** (like universities) that may have more vulnerabilities to discover and report.

6. **The standard is not yet official** but has been adopted by major Fortune 100 companies, suggesting it has practical value even before formal IETF approval.

---

**Source:** [Does Your Organization Have a Security.txt File?](https://krebsonsecurity.com/2021/09/does-your-organization-have-a-security-txt-file/) by Brian Krebs, Krebs on Security, September 20, 2021

