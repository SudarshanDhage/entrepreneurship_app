# Good Engineering Strategy Is Boring

A practical, bottoms-up approach to writing engineering strategy and vision: write five design documents, synthesize them into a strategy, then extrapolate five strategies into a vision.

## The Core Insight

**The reality:** Few companies understand their engineering strategy and vision. One consequence of this uncertainty is the industry belief that these documents are difficult to write. In some conversations it can feel like you're talking about something mystical, but these are just mundane documents.

**The truth:** Good engineering strategy is boring, and it's _easier_ to write an effective strategy than a bad one.

**The process:**
- To write an engineering strategy: Write five design documents, and pull the similarities out. That's your engineering strategy.
- To write an engineering vision: Write five engineering strategies, and forecast their implications two years into the future. That's your engineering vision.

**The key principle:** Durably useful engineering strategy and vision are the output of iterative, bottoms-up organizational learning. All learning contributes to your organization's strategy and vision, but your contribution doesn't have to be so abstract.

## Step 1: Write Five Design Docs

**What they are:** Design documents describe the decisions and tradeoffs you've made in specific projects. Your company might call them RFCs or tech specs. A good design document describes a specific problem, surveys possible solutions, and explains the selected approach's details.

**When to write them:** Whether a given project requires a design document comes down to personal judgment, but you should write design documents for:
- Any project whose capabilities will be used by numerous future projects
- Projects that meaningfully impact your users
- Any work taking more than a month of engineering time

**Why five?** A batch of five design docs is the ideal ingredient for writing an effective strategy because design documents have what bad strategies lack: detailed specifics grounded in reality. It's easy for two well-meaning engineers on the same team to interpret an abstract strategy in different ways, but it's much harder to stay misaligned when you're implementing a specific solution.

### Best Practices for Writing Design Documents

**1. Start from the problem.**
- The clearer the problem statement, the more obvious the solutions.
- If solutions aren't obvious, spend more time clarifying the problem.
- If you're stuck articulating the problem, show what you have to five people and ask them what's missing: fresh eyes always see the truth.

**2. Keep the template simple.**
- Most companies have a design document template, which is a great pattern to follow.
- However, those templates are often expanded to serve too many goals.
- Overloaded templates discourage folks from writing design documents in the first place.
- Prefer minimal design document templates that allow authors to select the most useful sections and only insist on exhaustive details for the riskiest projects.

**3. Gather and review together, write alone.**
- It's very unlikely that you personally have all the relevant context to write the best design document on a given topic.
- Before getting far into the process, collect input from folks with relevant perspective, particularly those who will rely on the output of your design document.
- However, be skeptical of carrying that collaborative process into writing the design document itself.
- Most folks are better writers than they are editors. This means it's usually harder to edit a group document into clear writing than to identify one author to write a clearer document.
- Gather perspectives widely but write alone.
- Just be careful not to fall in love with what you've written until _after_ you've reviewed it with others.

**4. Prefer good over perfect.**
- It's better to write a good document and get it in front of others than it is to delay for something marginally better.
- This is particularly valuable to keep in mind when giving feedback on other folks' designs.
- It's easy to fall into the trap of expecting their designs to be just as good as your best design.
- Particularly as you become more senior, it's toxic to push every design to meet the bar of your own best work.
- Focus on pushing designs to be good, rather than fixating on your own best as the relevant quality bar.

**Improving your design documents:** It takes a lot of practice to write great design documents. To improve yours, reread your designs _after_ you've finished implementing them, and study where the places where your implementation deviated from your plan—what caused those deviations? And of course, just keep writing more of them.

## Step 2: Synthesize Those Five Design Docs Into a Strategy

**The process:** After your organization has written five design documents, sit down and read them all together. Look for controversial decisions that came up in multiple designs, particularly those that were hard to agree on.

**Example:** A recent example was getting stuck debating whether Redis was appropriate as durable storage or only as a cache. Rather than starting from zero in each design document review, wouldn't it be easier if we reviewed our recent decisions about using Redis, reflected on how we made those decisions, and wrote them down as a strategy?

**What makes a good strategy:** Good strategies guide tradeoffs and explain the rationale behind that guidance. Bad strategies state a policy without explanation, which decouples them from the context they were made. Without context, your strategy rapidly becomes incomprehensible—why did they decide this?—and difficult to adapt as the underlying context shifts.

**The definition:** If you're a "Good Strategy, Bad Strategy" convert, you'll note this definition of strategy is the "diagnosis" and "guiding policies" sections, deferring "coherent action" to the design documents.

### Best Practices for Writing Strategy Documents

**1. Start where you are.**
- Working on strategy, it's easy to be paralyzed by the inherently vast ambiguity we work in, but you've just got to dive in and start writing.
- Waiting for missing information doesn't work: every missing document is missing for a good reason.
- Whatever you write will need to change, and if you write something particularly bad, you'll quickly realize the need to change it.
- Where you are now is always the best place to start.

**2. Write the specifics.**
- Write until you start to generalize, and then stop writing.
- If you can't be specific, wait until you've written more design documents.
- Specific statements create alignment; generic statements create the illusion of alignment.

**3. Be opinionated.**
- Good strategies are opinionated. If they aren't opinionated, then they won't provide any clarity on decision making.
- However, being opinionated on its own isn't enough, you also need to…

**4. Show your work.**
- In math classes growing up, you had to show your work to get full credit. Here too, you must show the rationale behind your opinions.
- Showing your work builds confidence in the first version of a document, but even more importantly, by showing your work, you make it possible for others to modify and extend your work as the underlying context shifts.

**What's worth writing:** Some of the best strategies you write may at the time feel too obvious to bother writing. "When should we write design documents?" is a strategy worth writing. "Which databases do we use for which use cases?" is a strategy worth writing. "Which services should page during off-hours?" is worth writing, too.

**The mindset shift:** As we leave behind the idea of strategy as a permanent brilliance, we can start to write far more of them, and we can write them more casually. If it ends up not being used, you can always deprecate it later.

## Step 3: Extrapolate Five Strategies Into a Vision

**The challenge:** As you collect more strategies, it'll become increasingly challenging to reason about how the various strategies interact. Maybe one of your strategies is to run less software and rely more on cloud solutions, but another one of your strategies is to prefer offloading complexity to the database whenever possible. How do you reconcile those strategies if you identify a database that would allow you to offload a great deal of complexity but that isn't offered by your cloud vendor?

**The process:** Take five of your recent strategies, extrapolate how their tradeoffs will play out over the next two to three years. As you edit through the contradictions and weave the threads together, you've written an engineering vision.

**The outcome:** The final version will give you what Tanya Reilly calls a robust belief in the future, which makes it easier to understand how your existing strategies relate to each other, and simplifies writing new strategies that stand the test of time.

### Best Practices for Writing Vision Documents

**1. Write two to three years out.**
- Companies, organizations and technology all change quickly enough that thinking too far into the future is fraught.
- It also doesn't work if you write a vision that expires in six months—how many strategies would you realistically write within that six month window?
- Try to focus on two to three years out, you can expand that horizon a bit if you're a fairly established company.

**2. Ground in your business and your users.**
- Effective visions ground themselves in serving your users and your business.
- That tight connection keeps the vision aligned with your leadership team's core values—users and business.
- Bad visions treat technical sophistication as a self-justifying purpose raison d'être—a view that is never shared by your company's leadership.

**3. Be optimistic rather than audacious.**
- Visions should be ambitious, but they shouldn't be audacious.
- They should be possible, but the best possible version of possible.
- Do write what you could accomplish if every project finished on time and without major setbacks.
- Don't write what you think would be possible with infinite resources.

**4. Stay concrete and specific.**
- Visions get more useful as they get more specific.
- Generic statements are easy to agree with but don't help reconcile conflicting strategies.
- Be a bit more detailed than you're comfortable with.
- Details in visions are often illustrative rather than declarative, giving a taste of the future's flavor rather than offering a binding commitment.

**5. Keep it one to two pages long.**
- The reality is that most people don't read long documents.
- If you write something five or six pages long, readers will start dropping off without finishing it (or will skim it very rapidly without engaging with the details).
- Force yourself to write something compact, and reference extra context by linking to other documents for the subset of folks who want the full details.

**Managing expectations:** After you finish writing your vision, the first step folks usually take is to share it widely across the engineering organization. There is so much work behind the vision—five design docs for each strategy, five strategies for one vision—it's hard _not_ to get excited when you're done. It's easy to get discouraged, then, when the response to your strategy will almost always be a muted one.

**Why the muted response?** There are a few reasons. First, the core audience for your vision is folks writing strategies, which is a relatively small cohort. Second, a great vision is usually so _obvious_ that it bores more than it excites.

**How to measure success:** Don't measure vision by the initial excitement it creates. Instead measure it by reading a design document from two years ago and then one from last week; if there's marked improvement, then your vision is good.

## When and Why

**What strategies are:** Strategies are tools of proactive alignment, that empower teams to move quickly and with confidence. Strategies allow everyone—not just the empowered few—to make quick, confident decisions that might have otherwise cost them a week of discussion. Strategies are also the bricks that narrow your many possible futures down enough that it's possible to write a realistic vision.

**When to write a strategy:** When you've rehashed the same discussion three or four times, it's time to write another strategy.

**When to write a vision:** When the future's too hazy to identify investments worth making, it's time to write another vision.

**When to skip it:** If neither of those sound like familiar problems—move on to other work for now and return later.

## The Prework: Clearing Your Head

**If you can't resist the urge:** If you can't resist the urge to include your most brilliant ideas into the process, then you can include them in your prework. Write all of your best ideas into a giant document, delete it, and never mention any of them again.

**Why this works:** Now that those ideas are out of your head, your head is cleared for the work ahead. The process should be grounded in what you've actually done, not what you wish you'd done.

## Key Takeaways

1. **Good strategy is boring:** It's easier to write an effective strategy than a bad one because effective strategies emerge from reality, not aspiration.

2. **The process is simple:** Write five design docs → synthesize into strategy → extrapolate five strategies into vision.

3. **Start from reality:** Design documents have what bad strategies lack—detailed specifics grounded in reality.

4. **Be specific, not generic:** Specific statements create alignment; generic statements create the illusion of alignment.

5. **Show your work:** Explain the rationale behind your opinions so others can modify and extend your work as context shifts.

6. **Vision is obvious:** A great vision is usually so obvious that it bores more than it excites. Don't measure success by initial excitement.

7. **Write when needed:** Write strategies when you've rehashed the same discussion three or four times. Write visions when the future's too hazy.

8. **It's bottoms-up learning:** Durably useful engineering strategy and vision are the output of iterative, bottoms-up organizational learning.

---

**Source:** [Write five, then synthesize: good engineering strategy is boring](https://lethain.com/good-engineering-strategy-is-boring/), Irrational Exuberance by Will Larson (November 26, 2020). Will Larson is the author of "An Elegant Puzzle," "Staff Engineer," "The Engineering Executive's Primer," and "Crafting Engineering Strategy."

