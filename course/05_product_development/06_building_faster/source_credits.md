# Source Credits

## Building Faster

- **Source:** Ellen's Newsletter (Substack)
- **Author:** Ellen Chisa
- **URL:** https://ellenchisa.substack.com/p/building-faster
- **Date:** 2025
- **Featured:** Ellen Chisa, Eliot Durbin (framing credit), Alice Wong (suggestion)
- **Examples:** Dark (OCaml/F#), Lola (individual vs. business travelers), Co-Star (Haskell)
- **Used In:**
  - Chapter 5: Product Development (Building Faster) - Building Faster

## Top 10 Reasons for Slow Velocity

- **Source:** SVPG (Silicon Valley Product Group)
- **Author:** Marty Cagan
- **URL:** https://www.svpg.com/top-10-reasons-for-slow-velocity/
- **Date:** 2025
- **Key Concepts:** Product velocity, slow delivery, organizational bottlenecks, product ownership, project management, release cycles, product discovery, UX design, product vision, dedicated teams, technical debt, architecture, team coordination
- **Key Insight:** Diagnostic framework for why product teams move slowly. Most organizations blame developer skills, but root causes are typically organizational/structural: (1) Lack of strong product owners - largest single reason, causes churn and morale issues. (2) Lack of strong project management - second biggest reason, need dedicated PM/ScrumMaster who is "pushy but not bossy" to remove impediments. (3) Infrequent release cycles - need releases no less frequently than every two weeks, requires regression test automation and release automation. (4) Not including lead engineers in discovery - need key participants from day 1 to contribute faster alternative approaches, prevents late-stage churn. (5) Not utilizing UX design in discovery - UX should be completed before items hit backlog, defined "pixel perfect," prevents waiting for designs/assets and "feed the beast." (6) Lack of product vision and focus - rapidly shifting roadmap/priorities cause churn, need clear big picture vision. (7) Lack of dedicated teams - treating engineers like chess pieces prevents expertise building and team relationships needed for velocity. (8) Lack of dedicated rapid response team - same teams doing sustaining/escalations and forward progress causes interruptions, need separate rapid response team. (9) Inflexible architecture/technical debt - architecture doesn't facilitate rapid evolution, must be attacked ongoing (can't fix overnight). (10) Missing holistic view - teams don't understand what others are doing and how parts fit together, causes thrashing/churn due to unclear dependencies/inter-relationships. Good news: each can be addressed. However, velocity less important than releasing good software that makes difference for business.
- **Used In:**
  - Chapter 5: Product Development (Building Faster) - Top 10 Reasons for Slow Velocity

## Speed Generates Quality

- **Source:** Medium (Jason Yip)
- **Author:** Jason Yip (Senior Manager Product Engineering at Grainger; ex-Spotify, ex-ThoughtWorks, ex-CruiseControl)
- **URL:** https://jchyip.medium.com/guiding-principle-speed-generates-quality-f0672db3e4bc
- **Date:** 2025
- **Key Concepts:** Product development, speed, quality, learning loops, iteration, organizational learning, velocity, agility
- **Key Insight:** Counterintuitive guiding principle: speed in learning generates quality, not the other way around. The ceramics teacher story: teacher divided class into two groups - "quantity" group graded on weight of pots produced (50 lbs = A), "quality" group graded on single perfect pot. Result: highest quality work came from quantity group. Why? Quantity group was churning out work and learning from mistakes, while quality group sat theorizing about perfection and had little to show. Core principle: Speed creates more opportunities for learning; learning generates quality. Mistake is believing that being more careful, taking longer, creates quality - sub-optimal because certain knowledge can only be acquired by releasing and making contact with the problem. This isn't mindless speed ("move fast and break things") but rather shortening learning loops. Learning faster is not about rushing; it's about making things safer and smoother. Key distinction: Smooth from perspective of "baton" (the work) ≠ smooth from perspective of "runner" (the worker). Smooth from perspective of baton has more impact on organizational learning speed. Two approaches: (1) Quality first - "be very careful," "do it right the first time," "people need to love first version" - leads to theorizing, little output, misses learning. (2) Speed first - "shorten learning loop," "make sure failure doesn't kill us" - produces iterations, learns from mistakes, generates better quality. Implications: Don't optimize for perfect first version, optimize for fast learning cycles. Create safety so failures don't kill you. Focus on smooth flow of work through system, not just individual speed. Fastest path to quality is through many cycles of learning, not careful planning of single attempt. Referenced: Art & Fear: Observations On the Perils (and Rewards) of Artmaking by David Bayles and Ted Orland (via Stratechery).
- **Used In:**
  - Chapter 5: Product Development (Building Faster) - Speed Generates Quality

## Never Rewrite Code From Scratch

- **Source:** Joel on Software (joelonsoftware.com)
- **Author:** Joel Spolsky (Co-founder of Fog Creek Software and Stack Overflow, CEO of Stack Overflow 2010-2019)
- **URL:** https://www.joelonsoftware.com/2000/04/06/things-you-should-never-do-part-i/
- **Date:** 2025
- **Key Concepts:** Code rewriting, refactoring, technical debt, software architecture, legacy code, code maintenance, incremental improvement, software development mistakes
- **Key Insight:** Rewriting code from scratch is "the single worst strategic mistake that any software company can make." Famous warning based on Netscape 6.0 rewrite disaster (3 years between releases, market share plummeted). Historical examples: Borland (dBase for Windows, Quattro Pro rewrite), Microsoft (Pyramid project for Word for Windows - shut down). Why programmers want to rewrite: Programmers are architects who want to bulldoze and rebuild, not do incremental renovation. Fundamental law of programming: "It's harder to read code than to write it" - explains why code always seems messy. Why code seems messy: Those "hairs" on functions are actually bug fixes - fixes for edge cases discovered through weeks of real-world usage (Nancy's bug, low memory conditions, floppy disk yanks, old Windows 95 compatibility). Each bug fix represents weeks of discovery plus days of reproduction/fixing. Cost of rewriting: (1) Throw away all knowledge, collected bug fixes, years of programming work. (2) Throw away market leadership - give competitors 2-3 years (long time in software). (3) Can't react to market - stuck shipping old code, can't make strategic changes. (4) Waste money writing code that already exists. Why old code is valuable: Old code has been used, tested, bugs found and fixed. Software doesn't rust. Idea that new code is better is patently absurd. Netscape code may have been "bad" but worked on many real-world systems. What's actually wrong with "messy" code: Three types of problems: (1) Architectural problems - code not factored correctly, can be solved incrementally by moving code, refactoring, changing interfaces. Example: Juno project rearchitected over several months without throwing away code. (2) Inefficiency - only affects small part, can optimize or rewrite just that part. "When optimizing for speed, 1% of work gets 99% of bang." (3) Ugliness - solve with macros, find/replace, not by rewriting. Example: FuckedString data type, underscore vs "m_" conventions. The rebuild fallacy: No reason to believe you'll do better - probably different team, will make same mistakes plus new ones. "Build one to throw away" mantra: Dangerous for large-scale commercial applications. Fine for experimental code (ripping up last week's function, refactoring class) but folly for whole programs. Key insight: Refactor incrementally, don't rewrite. Preserve knowledge while fixing problems.
- **Used In:**
  - Chapter 5: Product Development (Building Faster) - Never Rewrite Code From Scratch

