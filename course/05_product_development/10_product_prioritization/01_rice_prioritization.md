# RICE: Simple Prioritization for Product Managers

"Prioritization is a perennial challenge when building a product roadmap. How do you decide what to work on first?"

If you've put the effort into brainstorming new ideas, finding opportunities for improvement, and collecting feedback, you'll have a solid product roadmap full of good ideas. But the order in which you tackle those ideas deserves just as much thought. You need to take the time to prioritize well.

## Why Prioritization Is Difficult

So why is prioritizing a product roadmap so difficult? Let me count the ways:

- **It's satisfying to work on pet ideas you'd use yourself**, instead of projects with broad reach.
- **It's tempting to focus on clever ideas**, instead of projects that directly impact your goals.
- **It's exciting to dive into new ideas**, instead of projects that you're already confident about.
- **It's easy to discount the additional effort** that one project will require over another.

Even if you make it through this mental minefield intact, you're left with the tough task of consistently combining and comparing these factors across all project ideas. Thankfully, you don't have to do this in your head.

## RICE Score: A Simple Tool for Prioritization

This is where a scoring system comes in. A good prioritization framework can help you consider each factor about a project idea with clear-eyed discipline and combine those factors in a rigorous, consistent way.

Using a scoring system for prioritization in product management certainly isn't new. Systems designed to balance costs and benefits abound. But you can have a hard time finding one that allows you to usefully compare different ideas in a consistent way.

In response, we began developing our own scoring system for prioritization from first principles. After lots of testing and iteration, we settled on four factors, and a method for combining them.

## RICE: Four Factors for Assessing Priority

**RICE is an acronym for the four factors we use to evaluate each project idea: reach, impact, confidence and effort.**

### Reach

To avoid bias towards features you'd use yourself, **estimate how many people each project will affect within a given period.** For my team, it's "how many customers will this project impact over a single quarter?"

Reach is measured in number of people/events per time period. That might be "customers per quarter" or "transactions per month". **As much as possible, use real measurements from product metrics instead of pulling numbers from a hat.**

#### Examples

- **Project 1:** 500 customers reach this point in the signup funnel each month, and 30% choose this option. The reach is 500 × 30% × 3 = **450 customers per quarter.**
- **Project 2:** Every customer who uses this feature each quarter will see this change. The reach is **2,000 customers per quarter.**
- **Project 3:** This change will have a one-time effect on 800 existing customers, with no ongoing effect. The reach is **800 customers per quarter.**

### Impact

To focus on projects that move the needle on your goal, **estimate the impact on an individual person.** For my team, it's "how much will this project increase conversion rate when a customer encounters it?". Your team might replace this with another goal, such as "increase adoption", or "maximize delight".

Impact is difficult to measure precisely. So, I choose from a multiple-choice scale:
- **3** for "massive impact"
- **2** for "high"
- **1** for "medium"
- **0.5** for "low"
- **0.25** for "minimal"

These numbers get multiplied into the final score to scale it up or down.

Choosing an impact number may seem unscientific. But remember the alternative: a tangled mess of gut feeling.

#### Examples

- **Project 1:** For each customer who sees it, this will have a huge impact. The impact score is **3.**
- **Project 2:** This will have a lesser impact for each customer. The impact score is **1.**
- **Project 3:** This is somewhere in-between in terms of impact. The impact score is **2.**

### Confidence

To curb enthusiasm for exciting but ill-defined ideas, **factor in your level of confidence about your estimates.** If you think a project could have huge impact but don't have data to back it up, confidence lets you control that.

Confidence is a percentage, and I use another multiple-choice scale to help avoid decision paralysis:
- **100%** is "high confidence"
- **80%** is "medium"
- **50%** is "low"
- **Anything below that** is "total moonshot"

Be honest with yourself: how much support do you really have for your estimates?

#### Examples

- **Project 1:** We have quantitative metrics for reach, user research for impact, and an engineering estimate for effort. This project gets a **100% confidence score.**
- **Project 2:** I have data to support the reach and effort, but I'm unsure about the impact. This project gets an **80% confidence score.**
- **Project 3:** The reach and impact may be lower than estimated, and the effort may be higher. This project gets a **50% confidence score.**

### Effort

To move quickly and have impact with the least amount of effort, **estimate the total amount of time a project will require from all members of your team: product, design, and engineering.**

Effort is estimated as a number of **"person-months"** – the work that one team member can do in a month. There are many unknowns here, so I keep my estimates rough by sticking to whole numbers (or 0.5 for anything well under a month). **Unlike the other positive factors, more effort is a bad thing, so it divides the total impact.**

#### Examples

- **Project 1:** This will take about a week of planning, 1-2 weeks of design, and 2-4 weeks of engineering time. I'll give it an effort score of **2 person-months.**
- **Project 2:** This project will take several weeks of planning, a significant amount of design time, and at least two months of one engineer's time. I'll give it an effort score of **4 person-months.**
- **Project 3:** This only requires a week of planning, no new design, and a few weeks of engineering time. I'll give it an effort score of **1 person-month.**

## How Is a RICE Score Calculated?

So, to quickly summarise our four factors:

- **Reach:** how many people will this impact? (Estimate within a defined time period.)
- **Impact:** how much will this impact each person? (Massive = 3x, High = 2x, Medium = 1x, Low = 0.5x, Minimal = 0.25x.)
- **Confidence:** how confident are you in your estimates? (High = 100%, Medium = 80%, Low = 50%.)
- **Effort:** how many "person-months" will this take? (Use whole numbers and minimum of half a month – don't get into the weeds of estimation.)

Once you've estimated these factors, combine them into a single score so you can compare projects at a glance. Here's the simple formula:

**RICE Score = (Reach × Impact × Confidence) / Effort**

The resulting score measures **"total impact per time worked"** – exactly what we'd like to maximize. I set up a spreadsheet to automatically calculate the score for me as I estimate each factor.

Once the initial scoring is done, sort your list and re-evaluate. Are there projects where the score seems too high or too low? If so, reconsider your estimates and make changes, or accept that your gut instinct may be wrong.

RICE can help immensely when deciding between hard-to-compare ideas. It forces you to think about why a project idea will have impact, and to be honest about the effort that's needed to achieve it.

## How to Use RICE Scores Effectively

Of course, **RICE scores shouldn't be used as a hard and fast rule.** There are many reasons why you might work on a project with a lower score first:

- One project may be a **dependency for another project**, so it needs to happen first
- Another feature might be **"table stakes" to sell to certain customers**
- Sometimes you might want or need to work on projects "out of order"

**And that's okay!** With a scoring system in place, you can clearly identify when you're making these trade-offs.

A prioritization framework such as RICE will help you make better-informed decisions about what to work on first and defend those decisions to others.

---

**Source:** [RICE: Simple prioritization for product managers](https://www.intercom.com/blog/rice-simple-prioritization-for-product-managers/) by Sean McBride, Intercom Blog, January 5, 2018

