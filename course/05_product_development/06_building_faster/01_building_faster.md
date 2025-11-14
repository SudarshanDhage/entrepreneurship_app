# Building Faster

**"How quickly are you able to ship" is rarely about just writing code more quickly or hiring more engineers.**

Two of the indicators Ellen Chisa looks at with early stage companies are:
1. How quickly are they able to hire
2. How quickly are they able to build

Either not working tends to highlight a deeper issue.

There's still no silver bullet, but here are a few frameworks and tools engineers can use to build faster within an early stage company.

## Force Clear Priorities

Most people would say this isn't an engineering task. It's true, that in the ideal world, a founder will be focused on delivering a clear priority and engineers won't have to think about it too much. Alternatively, it might be a PM.

Pragmatically, **most of the time this doesn't happen**, but a great engineer can help force it. Anytime you're asked to build something, consider the range of approaches and provide them back to the asker with the tradeoffs highlighted.

Take an example that's seen way too many times: **"build our login system."**

This can reasonably be interpreted in a whole lot of ways:
- Build your own HTTP login system
- Use social auth with one or more of Google, Facebook, Github, etc.
- Integrate with an external provider: Okta, Auth0, or one of the many cool new auth startups

Since it's not clear, engineers can have a lot of different defaults:
1. Exactly what the stakeholder said
2. What would be "easiest" for them
3. What they've done before
4. What they think would be fun to learn/try
5. The optimal system

There's good arguments for all of them, but also big pitfalls:
- Lots of founders who aren't engineers say "build login with X, Y, Z" without any understanding that XYZ is nearly 3x the work of X, often for very little gain.
- Even with technical founders, they might have an "obvious" version in their mind that doesn't all match what the engineer thinks is "obvious."

**Great early stage engineers will instead highlight the different options and the resulting tradeoffs to force the stakeholder to make the business priority more clear.** The best engineers will also make a proposal for the best answer and suggest it directly.

> "I could stand up our own quick system in a couple days, but we know we're going to need auth no matter what we do. I don't think it's worth signing a contract to get enterprise Okta because I've heard it's a huge pain to integrate and we don't have enterprise grade users yet. Since our users are developers, I do think we should do social auth with Github, and that will take a little longer, but be more robust and expose us to fewer issues. I suggest we invest about a week to do that."

Ideally this type of framing won't take too long. It isn't meant to be a perfect assessment of how long, it's to highlight the important tradeoffs between options. **The more times you go through this loop, the more likely it is people will deliver better requirements to engineering in the future!** This will help you, but more importantly other engineers who aren't good at framing like this! It also prevents doing work beyond what the project needed, and protects against rework.

## Focus on What Will and Won't Change

At early stage companies things change A LOT. Being able to move fast can often mean having a sense of what will/won't change over time.

At the late stage, this will often be up to the PM. One engineer received this feedback: "The PM's job is to prevent churn. Since she isn't doing that, we've had to rip out code several times when the spec changed" at a much bigger company.

**At the seed stage, this is probably on the engineering team to sort out.** If you're building login, that's likely to hang around. You probably aren't going to change the core infrastructure you're using very often (AWS vs. GCP, your database, etc). On the other side of the spectrum, proposed UI can change every day until it ships.

There's two ways to keep this in mind, and both can be right depending on the circumstance:
- **Build what won't change first** to give people more time to sort out the frothier pieces
- **Build an artifact of what is likely to change** to force the conversation and get to the final answer before rebuilding

Either way, make sure you're at least considering what's going to change or not.

## Don't Think Too Far Ahead

This naturally falls out of "focus on what won't change," but on a longer time scale. Most things in an early stage company do change.

> A founder can nearly always tell a story about how the company will look at IPO, or after the next fundraise, but it's a trap when engineers start to believe that story is 100% true. The goal isn't to build the perfect system for that story. Despite the confidence that goes into it, it's a direction, not a crystal ball.

Early on at Lola, they optimized their system around scale of individual travelers. This took a fair amount of time, and also caused some substantial bugs. Within a year it became apparent that business travelers were the right market, meaning it was more important to organize around teams. Some of those original "long run" decisions had to be undone to account for the new future. **They would have been better off waiting to invest for the "long run" until they had more clarity on some of these directions.**

## Try Order of Magnitude Timeboxing

No matter what you're proposing to build, at some point along the line ask yourself **"what if I had to do it in an order of magnitude less time?"** (I usually use month vs. year, week vs. month, day vs. week, hour vs. day). It's unlikely you'll really get it done that fast but it'll give you a thought experiment that might yield some interesting ways to go faster.

The best case seen was that they figured out how to have their first external user building on top of Dark in six weeks instead of six months.

## Debug The Never-ending Tasks

The other one is to take a guess at how long something will take before you start.

This isn't about small discrepancies. Something takes six days instead of five? Could be a fluke, someone is learning to estimate still, someone got sick, lots of PRs from other coworkers, honestly this is no big deal. I think that level of optimization makes sense when you need reliability (way later than seed stage) or if you work at a consulting firm that bills by time. For an early stage product it just doesn't move the needle.

On the other hand, **something was supposed to take a week and a month later is still "almost done"? Dig in!** Nearly every engineering team has had some of these. It could be:
- The project was badly understood
- There is a lot more debt in that part of the codebase than anyone thought
- The skills of the engineer weren't matched to the project

Everyone just gets used to "oh yup that's still going" without realizing that **if every project looked this way the company would be 4x+ slower.** Spend the time on the big gaps, not the days here or there.

## Clear Goals for Code Review

Not everyone agrees on what code review is for. Answers from well respected engineers on the same teams range from "to make sure no one makes a mistake" to "to socialize and help others learn about parts of the codebase."

I won't get into which philosophy is best, but **the philosophy your early engineering team has should be externalized!** Otherwise you'll end up working at cross-purposes in reviews. It shouldn't be as formal as it is within a big company, but should help you make quicker decisions about what to comment on and what needs to be resolved.

Similar to "debug never-ending tasks" you should also **"debug never-ending reviews."** If reviews don't get eyes on them quickly, there are too many rounds of comments back and forth, or something has been up for a long time without progress, figure out why.

## Notice When You're Talking Past Each Other

I've seen a lot of technical discussions get derailed when two engineers are talking with good intent, but at cross purposes. These discussions often feel tense, and are actually about the identity (or skills) of the individuals rather than just about a specific solution. Two common causes are:
1. A deeply held belief about code
2. A fear of something that happened in a past role

If a conversation is emotional, goes on for a long time, loops in circles, or isn't coming to resolution, if either of you can notice it, it's good to take a break or loop in a third person. If it's happening in a Slack channel it's possible another teammate can notice it and proactively jump in. If at all possible, **the third person should try to facilitate both engineers understanding the ideas already in play instead of just adding a third technical opinion to the mix.**

It's often a case of everyone being heard and sharing root information, not finding the right answer to the technical challenge at hand. Figuring out the hot button issues is important. **When not resolved, these discussions can keep cropping up across projects, wasting huge amounts of time and emotional energy.**

By bringing this to the surface, sometimes a talented engineer has a deeply held belief that goes counter to what the team decides is their philosophy. At that point they should either:
1. Accept it won't be that way within this company, or
2. Find a team that aligns with their belief

Either way, the team will move faster as a result.

## Pick the Right Tools

Early on, Dark was written in OCaml which worked very well for prototyping a lot of the language features they needed, especially for the first year-ish when it was just a few people. A tradeoff became that employee onboarding took far longer than it might in a language that people were more comfortable with (Dark is now written in F#).

Another example: Co-Star, the astrology app, is written in Haskell. While the technical arguments for Haskell can be compelling, most people in the FP/Haskell community don't overlap with the astrology community. In this case, the tradeoff probably works because the team has only two backend engineers (maybe these are the two people in the overlap!) or perhaps the draw to work with the technology might outweigh the desire to work on the specific mission.

**For most companies, picking boring technologies people know will help you go faster.** Occasionally, you'll have a specific outlier that makes a lot of sense to move quickly within your space.

## Key Takeaways

1. **Force clear priorities.** Help stakeholders make business priorities clear by highlighting options and tradeoffs. Make a proposal for the best answer.

2. **Focus on what will and won't change.** Build stable infrastructure first, or build prototypes to force decisions on changing parts.

3. **Don't think too far ahead.** The founder's vision is a direction, not a crystal ball. Wait to invest in the "long run" until you have more clarity.

4. **Try order of magnitude timeboxing.** Ask "what if I had to do it in 10x less time?" to find faster approaches.

5. **Debug never-ending tasks.** Small discrepancies are fine, but if something takes 4x longer than expected, dig in and figure out why.

6. **Set clear goals for code review.** Externalize the philosophy so everyone works toward the same purpose. Debug never-ending reviews.

7. **Notice when talking past each other.** If discussions are emotional, circular, or not resolving, take a break or loop in a third person to facilitate understanding.

8. **Pick the right tools.** For most companies, boring technologies people know will help you go faster. Save the exotic tools for specific outliers.

---

**Sources:**
- [Building Faster](https://ellenchisa.substack.com/p/building-faster) - Ellen Chisa, May 22, 2022

