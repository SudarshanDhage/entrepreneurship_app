# Is Engineering Strategy Useful?

Exploring why engineering strategy matters, especially written strategy: there's always a strategy (even if unwritten), how strategies create impact, the costs of implicit strategy, and how strategy supports organizational and personal learning.

## The Core Question

While engineers frequently bemoan a missing strategy, their complaints rarely articulate why the missing strategy matters. Instead, it serves as more of a truism: the economy used to be better, children used to respect their parents, and engineering organizations used to have an engineering strategy.

**The fundamental insight:** There's _always_ an engineering strategy, even if there's nothing written down. The question isn't whether strategy exists—it's whether it's written down, whether it's effective, and whether it's appropriate for your organization.

## There's Always a Strategy

**The pattern:** I've never worked somewhere where people didn't claim there was no strategy. In many of those companies, they'd say there was no engineering strategy. Once I became an executive and was able to document and distribute an engineering strategy, accusations of missing strategy didn't go away; they just shifted to focus on a missing product or company strategy.

**Even at companies with clear strategies:** This even happened at companies that definitively had engineering strategies like Stripe in 2016, which had numerous pillars to a clear engineering strategy such as:
- Maintain backwards API compatibility, at almost any cost
- Work in Ruby within a monorepo, unless it's the PCI environment, data processing, or data science work
- Engineers are fully responsible for the usability of their work, even when there are product or engineering managers involved

**The reality:** Working there it was generally clear what the company's engineering strategy was on any given topic. That said, it sometimes required asking around, and over time certain decisions became sufficiently contentious that it became hard to definitively answer what the strategy was.

**William Gibson's insight:** In the same sense that William Gibson said "The future is already here – it's just not very evenly distributed," there is always a strategy embedded into an organization's decisions, although in many organizations that strategy is only visible to a small group, and may be quickly forgotten.

**The shift in thinking:** If you ever find yourself thinking that a strategy doesn't exist, I'd encourage you to instead ask yourself where the strategy lives if you can't find it. Once you do find it, you may also find that the strategy is quite ineffective, but I've simply never found that it doesn't exist.

## Strategy Is Impactful

**Creating alignment:** In "We are a product engineering company!", we discuss Calm's engineering strategy to address pervasive friction within the engineering team. The core of that strategy is clarifying how Calm makes major technology decisions, along with documenting the motivating goal steering those decisions: maximizing time and energy spent on creating their product.

**The impact:** That strategy reduced friction by eliminating the cause of ongoing debate. It was successful in resetting the team's focus. It also caused several engineers to leave the company, because it was incompatible with their priorities. It's easy to view that as a downside, but I don't think it was. A clear, documented strategy made it clear to everyone involved what sort of game we were playing, the rules for that game, and for the first time let them accurately decide if they wanted to be part of that game with the wider team.

**Ways strategies support organizations:**

**1. Concentrating company investment into a smaller space.**
- For example, deciding not to decompose a monolith allows you to invest the majority of your tooling efforts on one language, one test suite, and one deployment mechanism.

**2. Many interesting properties only available through universal adoption.**
- For example, moving to an "N-1 policy" on backfilled roles is a significant opportunity for managing costs, but only works if consistently adopted.
- As another example, many strategies for disaster recovery or multi-region are only viable if all infrastructure has a common configuration mechanism.

**3. Focus execution on what truly matters.**
- For example, Stripe's Sorbet strategy allowed a team of ten engineers to incrementally move the company's Ruby monolith towards static typing, without distracting the larger organization with the push.
- This was a difficult project, that could have consumed the entire organization for many months, but focus allowed a small team to accomplish the majority of early work.

**4. Creating a knowledge repository of how your organization thinks.**
- Onboarding new hires, particularly senior new hires, is much more effective with documented strategy.
- For example, the strategy for accessing user data requires that all access to user data is supported by a clear, user-understandable rationale for that access. While this might be obvious to new hires from larger companies, folks with only small company experience are likely to be completely unaware this is necessary. If it isn't documented, compliance to the policy will quickly decline.

**The bottom line:** There are some things that a strategy, even a cleverly written one, cannot do. However, it's always been my experience that developing a strategy creates progress, even if the progress is understanding the inherent disagreement.

## Inappropriate Strategy Is Especially Impactful

**The paradox:** While good strategy can accomplish many things, it sometimes feels that inappropriate strategy is far more impactful. Of course, impactful in all the wrong ways.

**Digg V4 example:** Digg V4 remains the worst considered strategy I've personally participated in. It was a complete rewrite of the Digg V3.5 codebase from a PHP monolith to a PHP frontend and backend of a dozen Python services. It also moved the database from sharded MySQL to an early version of Cassandra. Perhaps worst, it replaced the nuanced algorithms developed over a decade with a hack implemented a few days before launch.

**The consequences:** Although it's likely Digg would have struggled to become profitable due to its reliance on search engine optimization for traffic, and Google's frequently changing search algorithm of that era, the engineering strategy ensured we died fast rather than having an opportunity to dig our way out.

**A common pattern:** Importantly, it's not just Digg. Almost every engineering organization you drill into will have its share of unused platform projects that captured decades of engineering years to the detriment of an important opportunity. A shocking number of senior leaders join new companies and initiate a grand migration that attempts to entirely rewrite the architecture, switch programming languages, or otherwise shift their new organization to resemble a prior organization where they understood things better.

**Inappropriate versus bad:** When I first wrote this section, I just labeled this sort of strategy as "bad." The challenge with that term is that the same strategy might well be very effective in a different set of circumstances. For example, if Digg had been a three person company with no revenue, rewriting from scratch could have the right decision!

As a result, I've tried to prefer the term "inappropriate" rather than "bad" to avoid getting caught up on whether a given approach _might_ work in other circumstances. Every approach undoubtedly works in _some_ organization.

## Written Strategy Drives Organizational Learning

**The Carta example:** When I joined Carta, I noticed we had an inconsistent approach to a number of important problems. Teams had distinct standard kits for how they approached new projects. Adoption of existing internal platforms was inconsistent, as was decision making around funding new internal platforms. There was widespread agreement that we were in the process of decomposing our monolith, but no agreement on how we were doing it.

**The Navigators program:** Coming into such a permissive strategy environment, with strong, differing perspectives on the ideal path forward, one of my first projects was writing down an explicit engineering strategy along with our newly formed Navigators team, itself a part of our new engineering strategy.

**How it worked:** We developed a program at Carta to have explicitly named individuals who are technical leaders to represent key parts of the engineering organization. This representative leadership group made it possible to iterate on strategy with a small team of about ten engineers who represented the entire organization, rather than take on the impossible task of negotiating with 400 engineers directly.

**The value of written strategy:**
- Made it possible to explicitly describe the problems we saw, and how we wanted to navigate those problems
- Was an artifact that we were able to iterate on in a small group, but then share widely for feedback from teams we might have missed
- Could be revised and updated over time (for example, extending it to mention AI/LLMs, then revising again as we dive into agentic workflows)

**Disagreement is a feature:** A lot of people have disagreed with parts of the strategy, which is great: that's one of the key benefits of a written strategy, it's possible to precisely disagree. From that disagreement, we've been able to evolve our strategy. Sometimes because there's new information, and other times because our initial approach could be improved.

**Benefits for new hires:** New hires are able to disagree too, and do it from an informed place rather than coming across as attached to their prior company's practices. In particular, they're able to understand the historical thinking that motivated our decisions, even when that context is no longer obvious.

**Oral vs. written history:** With oral history, what you believe is highly dependent on who you talk with, which shapes your view of history and the present. With written history, it's far more possible to agree at scale, which is the prerequisite to growing at scale rather than isolating growth to small pockets of senior leadership.

## The Cost of Implicit Strategy

**Vulnerable to misinterpretation:**
- Information flow in verbal organizations depends on an individual being in a given room for a decision, and then accurately repeating that information to the others who need it.
- However, it's common to see those individuals fail to repeat that information elsewhere. Sometimes their interpretation is also faulty to some degree. Both of these create significant problems in operating strategy.

**The "two-headed organizations" solution:** Some years ago, I started moving towards a model where most engineering organizations I worked with have two leaders: one who's a manager, and another who is a senior engineer. This was partially to ensure engineering context was included in senior decision making, but it was also to reduce communication errors.

Errors in point-to-point communication are so prevalent when done one-to-one, that the only solution I could find for folks who weren't reading-oriented communicators was ensuring I had communicated strategy (and other updates) to at least two people.

**Inconsistency across teams:**
- At one company I worked in, promotions to Staff-plus role happened at a much higher rate in the infrastructure engineering organization than the product engineering team.
- This created a constant drain out of product engineering to work on infrastructure-shaped problems, even if those problems weren't particularly valuable to the business.
- New leaders had no idea this informal policy existed, and they would routinely run into trouble in calibration discussions. They _also_ weren't aware they needed to go argue for a better policy.
- Worse, no one was sure if this was a real policy or not, so it was ultimately random whether this perspective was represented for any given promotion: sometimes good promotions would be blocked, sometimes borderline cases would be approved.

**Inconsistency over time:**
- Implementing a new policy tends to be a mix of persistent and one-time actions. For example, let's say you wanted to standardize all HTTP operations to use the same library across your codebase. You might add a linter check to reject known alternatives, and you'll probably do a one-time pass across your codebase standardizing on that library.
- However, two years later there are another three random HTTP libraries in your codebase, creeping into the cracks surrounding your linting.
- If the policy is written down, and a few people read it, then there's a number of ways this could be nonetheless prevented. If it's not written down, it's much less likely someone will remember, and much less likely they'll remember the rationale well enough to argue about it.

**Hazard to new leadership:**
- When a new Staff-plus engineer or executive joins a company, it's common to blame them for failing to understand the existing context behind decisions. That's fair: a big part of senior leadership is uncovering and understanding context. It's also unfair: explicit documentation of prior thinking would have made this much easier for them.
- Every particularly bad new-leader onboarding that I've seen has involved a new leader coming into an unfilled role, that the new leader's manager didn't know how to do. In those cases, success is entirely dependent on that new leader's ability and interest in learning.

**Succession planning:** In most ways, the practice of documenting strategy has a lot in common with succession planning, where the full benefits accrue to the organization rather than to the individual doing it. It's possible to maintain things when the original authors are present, appreciating the value requires stepping outside yourself for a moment to value things that will matter most to the organization when you're no longer a member.

**Information herd immunity:** A frequent objection to written strategy is that no one reads anything. There's some truth to this: it's extremely hard to get everyone in an organization to know something. However, I've never found that goal to be particularly important.

My view of information dispersal in an organization is the same as Herd immunity: you don't need everyone to know something, just to have enough people who know something that confusion doesn't propagate too far.

So, it may be impossible for all engineers to know strategy details, but you certainly can have every Staff-plus engineer and engineering manager know those details.

## Strategy Supports Personal Learning

**The individual benefits:** While I believe that the largest benefits of strategy accrue to the organization, rather than the individual creating it, I also believe that strategy is an underrated avenue for self-development.

**1. Creating strategy builds self-awareness.**
- Starting with a concrete example, I've worked with several engineers who viewed themselves as extremely senior, but frequently demanded that projects were implemented using new programming languages or technologies because they personally wanted to learn about the technology.
- Their internal strategy was clear–they wanted to work on something fun–but following the steps to build an engineering strategy would have created a strategy that even they agreed didn't make sense.

**2. Strategy supports situational awareness in new environments.**
- Wardley mapping talks a lot about situational awareness as a prerequisite to good strategy. This is ensuring you understand the realities of your circumstances, which is the most destructive failure of new senior engineering leaders.
- By explicitly stating the diagnosis where the strategy applied, it makes it easier for you to debug why reusing a prior strategy in a new team or company might not work.

**3. Strategy as your personal archive.**
- Just as documented strategy is institutional memory, it also serves as personal memory to understand the impact of your prior approaches.
- Each of us is an archivist of our prior work, pulling out the most valuable pieces to address the problem at hand. Over a long career, memory fades–and motivated reasoning creeps in–but explicit documentation doesn't.

Indeed, part of the reason I started working on this book _now_ rather than later is that I realized I was starting to forget the details of the strategy work I did earlier in my career. If I wanted to preserve the wisdom of that era, and ensure I didn't have to relearn the same lessons in the future, I had to write it now.

## Summary

We've covered why strategy can be a valuable learning mechanism for both your engineering organization and for you. We've shown how strategies have helped organizations deal with service migrations, monolith decomposition, and right-sizing backfilling. We've also discussed how inappropriate strategy contributed to Digg's demise.

**Two key themes to emphasize:**

1. **There's always a strategy, even if it isn't written down.**
2. **The single biggest act you can take to further strategy in your organization is to write down strategy so it can be debated, agreed upon, and explicitly evolved.**

**The reality:** Discussions around topics like strategy often get caught up in high prestige activities like making controversial decisions, but the most effective strategists I've seen make more progress by actually performing the basics: writing things down, exploring widely to see how other companies solve the same problem, accepting feedback into their draft from folks who disagree with them. Strategy _is_ useful, and doing strategy can be simple, too.

---

**Source:** [Is engineering strategy useful?](https://lethain.com/is-engineering-strategy-useful/), Irrational Exuberance by Will Larson (January 30, 2025). This is a chapter from "Crafting Engineering Strategy." Will Larson is the author of "An Elegant Puzzle," "Staff Engineer," "The Engineering Executive's Primer," and "Crafting Engineering Strategy."

