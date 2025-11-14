# Simple Product Management Tricks

_"I'm a fairly poor product manager. It's not a discipline I've practiced much, so I haven't developed any of the skills I'd need to be good at it. Constitutionally, I'm too easily distracted by the 'ooh shiny' to keep a solid focus on the most important parts of a product."_

Here are a few simple moves to use when you need to wear a product hat. Far from expert advice, just a few tricks that help you be not completely useless as a product manager.

## Perform an Effort/Impact Analysis

This is a technique for long-term planning; use this when you need to help a team decide what to focus on from a backlog or set of ideas.

**The technique:** Lay out potential work on a grid that maps difficulty against impact:

- **Impact** on the vertical axis (low at bottom, high at top)
- **Difficulty** on the horizontal axis (low at left, high at right)

When doing this, it's very fast and loose: don't worry too much about precise definitions of "difficulty" or "impact"; just quickly throw things up on the matrix.

**What's remarkable is that often that's all it takes for a plan to emerge:**
- Items in the upper-left area (high impact, low effort) = obvious wins
- Items in the bottom right (low impact, high effort) = obvious "no's"
- Then pick a few items from the middle, as you have appetite for more work, and there's a plan

It's amazing how effective this technique is in getting a team to agree on a set of work in a short amount of time.

## Timebox Hard-to-Estimate Work

A common challenge: how to handle work that has huge unknowns. For example, think about migrating a legacy codebase: anyone who's worked on a project like this knows that unknowns dominate the timeline. It can be nearly impossible to know upfront exactly what tasks will be required.

**The solution:** Timeboxing - picking an arbitrary length of time (a week or two, usually) and just seeing how far you get. At the end of a timebox, you'll have more knowledge about the work. Review progress, and make better-informed decisions about how to proceed.

**Timeboxing is powerful because it approaches estimation from a different direction:**
- Instead of: "how long will X take?"
- Timeboxing asks: "what can we do in two weeks?"

Timeboxing is also very useful for projects that clearly can't be completed in a reasonable amount of time. For example, think about a team with a massive backlog of bug reports. It might be untenable to spend the time required to drive the queue to zero, but spending one day a week driving the queue down might be fine.

Timeboxes are a great way of making progress despite mountains of work or significant unknowns.

## Write Playbooks Before Automation

Most software developers know the temptation to automate: when we see some time-consuming manual process, it's extremely tempting to try to convert it into code.

**The problem:** Automation isn't always the slam-dunk we think it will be. We _know_ that writing code to automate a process isn't necessarily as easy as we'd like it to be; but we also _know_ that the process is complex, error-prone, messy, or otherwise not great to leave as a manual process.

**The solution:** Playbooks are the middle ground. When you see a process like this, instead of either doing nothing or just diving in and writing code, first write a playbook. A playbook is nothing more than a set of instructions for performing the task – a "recipe" if you will. The key is to be as specific as possible. If this is some sort of task that involves code, you can even include bits of code or shell commands that someone following the playbook could copy and paste.

**This gets a few steps closer to the goals of automation** – consistency, repeatability, reliability – at a fraction of the effort. And, if you later decide that automation is worth the effort, the playbook serves as a detailed specification for your code.

---

**Source:** [Simple Product Management Tricks](https://jacobian.org/2021/oct/20/simple-pm-tricks/) by Jacob Kaplan-Moss, October 20, 2021

