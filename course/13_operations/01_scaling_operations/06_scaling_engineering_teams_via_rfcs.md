# Scaling Engineering Teams via RFCs: Writing Things Down

How a simple process of writing down plans, sharing them widely, and getting feedback scales engineering teams from tens to thousands of engineers. A practice successfully used at Uber and other large tech companies.

## The Problem: Two Common Planning Issues

When working at large companies like Microsoft or smaller ones like Skyscanner, there have been two things related to planning that have always been problematic:

1. **Lack of visibility** on others building or having built the same thing as your team
2. **Tech and architecture debt** accumulated due to different teams building things very differently, both approach-wise and quality-wise

## The Solution: A Five-Step RFC Process

**What if there is a way to tackle both these issues using a few simple steps?** Here they are:

### 1. Do planning before building something new

This can be in-person whiteboarding or just talking it through with the team members, as long as you're all clear on how you will get things done.

### 2. Capture this plan in a short, written document

Once it is clear to the team how and what you do, it should be relatively quick to write down the "how". Don't go overboard.

### 3. Have a few, select people approve this plan before starting work

Similar to how it's a good quality gate to only merge a pull request after someone does a review on it, it makes a huge difference if before starting work on a project, a few, relevant people validate the planned work. These can be senior engineers, people on a team who will use the feature and so on.

### 4. Send this planning document out to all engineers in the company

Let anyone and everyone comment on it. Yes, this the step that probably sounds crazy.

### 5. Have everyone follow the above steps

For every project that is beyond some super trivial complexity and iterate on a lightweight, RFC-like process so it works well for your org or company.

**As unlikely it might sound, the above process both works and scales really well**, from a handful of engineers to teams of thousands. It addresses not only issues on visibility or reducing tech/architecture debt, but also spreading knowledge and having engineers be more engaged day to day.

This is the one, simple process recommended for any small or medium tech team to do, especially if they are in a growth phase. It's also the process successfully used and iterated on at Uber, going from tens of engineers to a couple of thousand ones.

## The Power of Writing Things Down

**Writing and sharing that writing with others creates accountability.** It also almost always leads to more thorough decisions.

**Examples of the power of writing:**
- A simple way to increase code quality? Do code review in writing, before merging.
- A simple way to have a meeting be less of a waste of time? Have a written agenda before the meeting, then write up and send out decisions and actions afterwards.
- A simple way to run projects with fewer surprises? Have the team write down what they are planning to do and share it with others.

**The efficiency argument flipped:**

Engineers hate time wasters. Documentation is often seen as one of these time wasters, mostly because it is boring to do. Planning is often seen as a kind of documentation, so there is a natural tendency to just skip this step for efficiency.

**However:** If everyone agrees how the project should be done then writing the approach down should be a piece of cake. It just needs to capture the shared understanding on:
- What the approach is
- What architecture changes will be made
- What the tricky parts are

Someone from the team should be able to do this in a few hours, the other team members giving a thumbs-up after reading through it.

**Reality check:** Usually, this being less straightforward reveals important issues:

- "This is not what I meant when we talked."
- "What about this important edge case we forgot?"
- "If we change this here, it could break this other part of the system"

These things often come up when writing the plan down. **It's great to have these discussions before having the same realizations when the project is halfway done.**

**What about when people don't agree with how the project should be done or there are just a lot of changes?** That already sounds like a project that will take a lot longer than people think - writing down things at least should give a clearer picture.

## Reviewers and Spreading Knowledge Across the Organization

**Writing for others vs. organizing thoughts:**

While writing is a good way to organize one's thoughts, it is a very different exercise when we write for someone else to understand. It's a good idea to specify who needs to read this document and give a thumbs-up. Once the plan is written-up, the surest way to make sure the people actually read the doc is to require them confirming just this - in writing, via e.g. a comment.

### Sending Plans to Everyone (Yes, Really)

**The part of sending out the plan on how this project will be built, to all the engineering organization, via email, is something that can sound crazy.** People often worry about this creating a lot of noise.

**Reality:** This is both true and not. The noise levels will definitely increase. Thankfully, email filters are easy to create - just make it easy to filter for these kinds of emails. At the same time, there are a lot less project plans being sent out, even with an engineering size in the hundreds or thousands, than people typically expect.

### Cultural Impact

**The type of information pushed to people in an organization shapes the culture considerably.** Having an organization with a culture to push engineering plans to everyone - for example, via email - and invite anyone to comment sets a tone of trust and responsibility.

**Personal experience at Uber:** During the first few months at Uber, reading planning docs from a variety of teams and chiming into ones where there was relevant domain knowledge (e.g. on the technology) led to learning a lot more about what other teams worked on than in years working at a large company where this information was not visible. To this day, still looking through plans that teams make provides a sense of what is going on outside the immediate bubble.

### Self-Balancing and Self-Correction

**Allowing anyone and everyone to chime in is a key part of keeping a consistent engineering bar across the organization.**

At Uber, there have been multiple cases of people on one side of the organization realizing that another team on the other side is planning to do something similar to what they have done, but with a very different approach, often with a different quality bar.

**Example:** A US team building a new feature might have not considered other parts of the world and a team in India pointing out gaps in their localization approach.

**The teams having transparency, self-balancing and self-correction happens quite naturally.**

## Tailoring the Process via Iteration

At Uber, this process has been used from the early years. Details of how this planning and review process has worked has been refined as the company grew and matured.

**Evolution:**
- What started out as an email to every engineer
- Changed into mailing lists per domain (backend, mobile, web)
- Templates built by engineers to help convey information in a more consistent matter
- As the company grows to the thousands of engineers, more tooling is being built to make the process of searching and approving even easier

### Template Evolution

**An interesting part of the iteration is the evolution of templates.** People who review many engineering proposals often had the same type of questions. Questions like:
- "What is the motivation to do this work?"
- "How will this be tested?"
- "Will any architecture changes be made here?"

These were very common questions. Seeing the repeat on these, engineers came up with templates that keep being updated to make reading and writing these plans easy.

**Backend Template:**
- List of approvers
- Abstract (what is the project about?)
- Architecture changes
- Service SLAs
- Service dependencies
- Load & performance testing
- Multi data-center concerns
- Security considerations
- Testing & rollout
- Metrics & monitoring
- Customer support considerations

**Mobile/Web Template:**
- List of approvers
- Abstract (what is the project about?)
- UI & UX
- Architecture changes
- Network interactions detailed
- Library dependencies
- Security concerns
- Testing & rollout
- Analytics
- Customer support considerations
- Accessibility

**Key principle:** Iterating and customizing to the needs of the engineering team is key. The templates started to include important things they cared about. Things like reliability, scale, security. At Uber, they've built many smaller services, so things to consider when doing so - like load and performance testing or SLAs - are part of that domain. When accessibility became a big focus for mobile, that section made it into the template.

## A Process That Scales

At Uber, they called this process **RFC - Request for Comments**, given the many similarities it has with the Request For Comments publication process in the tech community.

**Why it stuck:**
- Started early enough - when the engineering team was small
- Helped scale knowledge and eliminate silos
- As the company kept growing rapidly, it scaled remarkably well, from tens of engineers to the low thousands
- Starting at a few thousand engineers, new challenges arise with this kind of process, which is a good problem to have by itself

**Real-world example:** You can see Uber's RFC process happen in the open by checking some of their open source projects, such as BaseUI. BaseUI is a web design system comprised of modern, responsive, living components. All RFCs are published and reviewed publicly. Development only starts after the RFC is approved.

### Not Unique to Uber

**Is this process unique to Uber? Far from it.** Larger tech companies, like Google, Facebook, Microsoft or Amazon all came up with something that resembles some level of RFC process.

- **Google** calls it design docs
- **Architecture Decision Records (ADRs)** are also a good format to use

**The scale on how thorough the documentation should be, who the docs are pushed to, how strictly it is reviewed or how standardized it is across different orgs is different for all companies.**

**Key takeaway:** If you're at a tech company where planning is still adhoc, without a structured way on recording/distributing it, **one of the things that will help engineering scale greatly is having a type of RFC process in place early on**. Just give it a try and iterate on how you do it. That's how it always starts.

---

**Source:** [Scaling Engineering Teams via RFCs: Writing Things Down](https://blog.pragmaticengineer.com/scaling-engineering-teams-via-writing-things-down-rfcs/) by Gergely Orosz, The Pragmatic Engineer, originally published October 3, 2018, last updated September 21, 2022

