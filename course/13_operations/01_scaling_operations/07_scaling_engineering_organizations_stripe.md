# Scaling Engineering Organizations

Lessons learned from scaling Stripe's engineering team, covering recruiting, hiring, training, onboarding, and engagement/retention.

## Introduction

At Stripe, they think a lot about scale. As they've scaled their products to process billions of dollars a year for millions of businesses, they've also needed to scale their engineering team.

**The temptation:** For fast-growing companies to build their engineering team as quickly as possible.

**The risks with rapid growth:**
- Creating silos
- Diminishing user impact per engineer over time
- Limiting ability to change how you work quickly to respond to changing user needs

**Stripe's approach:** They've deliberately chosen to add engineers at a slower rate than the growth of their user base and instead take an iterative approach to recruiting and developing their team. They were able to keep teams small, invest more in each person and nimbly change their ways of working as needs changed.

**Key principle:** Since what works for fifty engineers may not work for ten or a thousand, they've built a culture of feedback and iterative thinking that enables them to continually make changes as they grow.

## Recruiting and Hiring

### Continuously Evolve Your Process

Every company's recruiting process and hiring needs are unique. When Raylene Yung first joined Stripe, they had just one dedicated technical recruiter supporting dozens of referrals and new applicants. Since then, they've improved, added or replaced almost every part of the recruiting process and nearly quadrupled the size of their engineering team.

**Timeline:** Processes run well for about six to nine months before they need to update them.

**To safely experiment and evolve your recruiting process, you need to:**
- Define a recruiting plan to meet organisational needs
- Build consistency into your recruiting process to ensure efficiency and fairness
- Never lose sight of candidate experience: No matter the outcome, you should leave a positive impression of your company and team
- Revisit your recruiting process on a regular basis to measure progress and make changes as needed

### Build a Consistent Recruiting Platform

**Consistent recruiting increases efficiency, prevents bias and raises the hiring bar.** It's important to clearly define the process you use to identify, evaluate and hire candidates; the more consistency you introduce, the more you can rely on predictable outcomes, use data to understand what's working well and change the things that aren't.

**Training:** They run regular training sessions for new hiring managers alongside their recruiting team. Clear documentation helps train new managers and share best practices, even for small details like when to email candidates and how written offers get sent. Every hiring manager, recruiter and interviewer is aware of what they're responsible for in the interview pipeline.

**Training value:** Training sessions are valuable for all levels of experience; even new managers who have led recruiting initiatives at other companies remark how useful it is to learn exactly how Stripe approaches hiring. This is as much about consistency as it is making your own team feel confident and effective.

**Interview design:** Their interview process is drawn from industry studies and their own best practices. Their questions seek to understand how people approach real world problems, rather than testing for esoteric skills you might demonstrate on a whiteboard.

**Examples:**
- **Bug Squash engineering interview:** Candidates and interviewers sit side by side to solve a real historical bug in an open-source project while working in the candidate's programming language of choice
- **Team Role Plays (for engineering managers):** Simulate working through issues during a one-on-one conversation with a teammate

**Standardized questions using rubrics:** They standardize questions using written rubrics that define exactly how to run each interview, evaluate those questions consistently and compare scores across candidates. A good rubric outlines the goals of the interview and provides clear criteria to evaluate the candidate's performance.

**Rubric example — Communication skills:**

**4 (Exceptional):** The candidate is extremely clear and provides specific details supporting their general claims. The candidate communicates their personal trajectory and impact as well as the relation to projects/teams/companies they were working on. The candidate fluidly adapts to the conversation and prompts of the interviewer.

**3 (Good):** The candidate's communication is consistently clear, making high-level points and substantiating them with specific examples and details. They effectively engage in a two-way conversation with the interviewer.

**2 (Needs improvement):** The candidate's communication is not consistently clear. They provide details in some but not all cases when asked, or the details they do provide do not back their higher-level points, or most details are about something other than their own work. The candidate may be an inconsistent partner in the two-way conversation.

**1 (Poor):** The candidate's communication is scattered, erratic or otherwise unclear. The candidate does not provide details or specifics, even when asked, or talks exclusively about things other than their personal work and contributions. The candidate may not be able to enter an effective two-way conversation with the interviewer.

**Rubric integration:** They integrate rubrics directly into their applicant tracking system so interviewers can consistently reference them as they're providing feedback.

**Unconscious bias training:** In addition to building clear rubrics, they began unconscious bias training to maintain consistency and objectivity.

**Candidate Review process:** They incorporated their standardized questions into a new Candidate Review process they use to give feedback to interviewers and hiring managers once interviews are completed.

Candidate Review is a recurring meeting with a set of experienced reviewers that's used to examine all interview results. In each session, reviewers read over results, give feedback to individual interviewers and identify ways they can improve the overall process. Reviewers don't second guess decisions, but do ensure that everyone leaves sufficiently detailed feedback and makes decisions based only on information they see.

**Starting Candidate Review:** Candidate Review started small, and Raylene personally attended every session for six months to help train new reviewers, read feedback and learn from first-hand observations. Engineers appreciated knowing someone was personally reading their notes, and they quickly saw the quality and consistency of feedback improve – both in level of detail and adherence to rubrics. Crucially, this helped them make several improvements to the interviews themselves.

### Define Clear Hiring Goals and Effective Processes

**Clear goals enable you to measure success** and make the right changes to your process when needed. If you rely primarily on a passive funnel of inbound applicants and referrals, you can end up hiring whoever walks through the door rather than who you really need right now.

**Stripe's evolution:**
- **Early years:** Hired primarily generalist engineers who could work efficiently across the stack
- **Later:** As they tackled more specialized problems (scaling secure credential storage infrastructure, building international mobile payment flows), they had to change their approach to attract specialists

**Frontend specialist example:** As a hiring manager for frontend specialists, Raylene frequently met candidates who would tell her, "Stripe doesn't need any frontend engineers; you're an API company." In one interview, while explaining how they work on problems beyond API development, it was clear she was quickly losing the candidate's interest; they couldn't visualize what they'd work on if they joined. She ran to grab her laptop and spent 30 minutes showing them live demos of their web and mobile dashboards. The pitch worked: They immediately began to ask questions and make product suggestions. Shortly afterward, they interviewed and joined the company.

**This experience inspired them** to design a new candidate experience for frontend engineers that didn't require improvisation. Today they have many frontend engineers across Stripe – some are embedded directly on product teams and others build shared components and infrastructure that empower everyone to write better frontend code quickly and easily.

**Key principle:** As you expand into different product areas, it's important to bring the same structure you initially built for generalists and tailor it to more specialized roles.

**They started small:** They started with a small number of roles (infrastructure, frontend engineering) to understand how to retool their recruiting operations one at a time. They now hire across many different pipelines, ranging from Android to machine learning to security. These changes have steadily increased their offer acceptance rates and they now have specialists in every pipeline.

**Each detail affects every part of the recruiting process:**
- Posting different job descriptions publicly
- Deciding which recruiters are staffed against which roles
- Creating specialized interview questions, rubrics and candidate preparation guides for each role

**Example — Elements team:** When they launched Elements, their UI toolkit for payment flows, the Elements team had benefitted from the collective experience of specialists spanning security, frontend engineering and user experience to tackle an extensive list of challenges: secure isolation of card details with iframes, resolving browser-specific bugs, adding internationalisation, incorporating modern JavaScript API design and optimising conversion flows.

### Create a Great Candidate Experience

**The interview process defines every candidate's first impression** of how your company and engineering teams operate. They strive to provide a great experience for everyone, no matter how well they perform in their interviews.

**Benchmarking:** They recently conducted a private poll across several recruiting teams in the San Francisco Bay Area. Based on these benchmarks, recruiting funnels have an acceptance rate between 12–20% from the onsite interview to an accepted offer.

**Key insight:** For every hire, four to seven people go work at other companies and take their interview experience with them – this means there's a small army of people out there who implicitly represent your company and what you stand for, even if you never talk to them again. You are very likely to hire people from your candidates' social and professional networks; if you leave a great impression, even those who don't go on to work for your team can help generate great referrals.

**Best practices:**
- Before the interview, share written guides to help them understand Stripe's culture and prepare for the interview
- Engineers choose from a number of different programming languages and can use their own laptop and development environment
- Afterward, send follow-up anonymous surveys to candidates to learn more about their experience and identify ways to improve

**Feedback loops:**
- Speak with every candidate after they interview, even the ones that don't end up working at Stripe
- For those who don't accept the offer, schedule a call to understand their choice and how they felt about the role
- When they don't extend an offer, recruiters give candidates personalized feedback to help them learn from their experience

**Results:** Their surveys have shown that candidates have a good experience interviewing at Stripe: Those without offers rate their experience an average of 4.1 out of 5, and people who do get offers average 4.5. Even more striking, candidates who don't join Stripe often go on to refer their friends and colleagues to them later.

## Training and Onboarding

### Spin Up Your New Hires Effectively

**Growing teams work incredibly hard to hire new employees, but can overlook helping new teammates succeed once they start.** Joining a high-growth startup can be an intimidating experience, and without guidance, new hires have to work twice as hard to learn what they need to be productive.

**Stripe's early mistake:** In Stripe's early days, they made the mistake of not investing enough in onboarding. Employees defined their ramping up period as a sink-or-swim experience. When Raylene first joined Stripe, several teammates described this lack of support as a test – they assumed it was the company's way of evaluating everyone again after they started. That was not the case, but by not investing enough in an onboarding program, they implicitly said that people were on their own; it's easy to turn mistakes into accidental company norms.

**Today:** They invest significant time and energy in onboarding and helping all new hires grow their impact.

### Invest in Dedicated Training and Onboarding Programs

**The first few months are critical for new hires.** Asking an engineer to build a feature in their first week is tempting, but investing in onboarding and training makes for happier and more productive teammates.

**Stripe 101 — General onboarding:**

For all new employees, they developed Stripe 101: a general onboarding program that connects new hires across the company. In just a few weeks, people learn about Stripe by:
- Attending classes
- Meeting with cofounders
- Building a Stripe integration
- Answering support tickets
- Getting an early opportunity to collaborate with people in many different functions at the company

**Scale:** This operates at impressive scale, with over 30 sessions led by 82 instructors from across the organisation. Last year, over 200 Stripe employees went through the program.

**Results:**
- 100% of new Stripe employees were able to summarise the function of at least three Stripe products by the end of Stripe 101
- 94.5% of new Stripe employees felt their first week at Stripe was a positive experience and felt the Stripe 101 curriculum was an effective use of time
- 90% of new Stripe engineers understood the components of the Stripe stack by the end of the program

**Network building:** New hires also graduate with an immediate network of peers who work in different functions across Stripe. This helps them navigate the organisation in a personal way as they tackle projects later in their career at the company.

**/dev/start — Engineering-specific onboarding:**

Stripe 101 is helpful for general-purpose knowledge, but they saw the need for an additional onboarding experience for new engineers. They enjoyed meeting people across the company, but were anxious to spend time with technical teams and diving into code.

They developed a new program to introduce them to their technical stack by solving a practical problem in their main application codebase. They called it **/dev/start** and started with a small pilot, featuring a handful of new engineers, volunteer mentors, projects pulled from team backlogs and one-on-one feedback. Within months, it expanded to multiple organisations and was soon used for all of engineering.

**Today:** They group new hires into temporary virtual teams for three to four weeks. Teams work with a dedicated mentor to learn about their development process while shipping a concrete tool or product improvement.

**Mentor benefits:** Experienced Stripe engineers gain project leadership and mentorship experience by serving as mentors – they sit with the team, break the project down into tractable tasks, answer both technical and product questions, review code and serve as a bridge to the rest of engineering.

### Don't Forget About Soft Skills and Culture

**Psychological safety** is the shared belief by team members that it's safe to take risks and share knowledge to support one another. In Google's Project Aristotle, a study to understand the secrets of effective teams, psychological safety was identified as the most important factor to team success.

**They aim to create this safety** by writing guides to culture and group norms; they cover both general communication and team-specific practices.

**Stripe 101 includes a class called "Communicating at Stripe"** that describes company mailing lists, best practices for email and bug trackers, but also non-obvious communication patterns like how to schedule meetings. Norms for calendars may seem like common sense, but they carry key cultural knowledge: Understanding them can help people avoid embarrassing scheduling errors or discover important events.

**Example — Email at Stripe:**
- Use email for non-urgent messages. If you need a quick response that can't wait until your recipient checks their email, use Slack
- If you're going to be out of the office (OOO), consider putting up an autoresponder to tell people your response timeline and who's covering for you
- You should send a shipped@ email when wrapping up a unit of work
- You shouldn't lurk into people's threads unnecessarily
- Open communication at Stripe only works if we create and promote an environment that feels safe to all Stripe employees

**Engineering teams provide specialized guides** for specific tools (e.g. GitHub or JIRA) or common practices like code review. These act as a source of truth and allow teams to collaboratively agree on their processes up front, reducing ongoing debate or confusion. Self-serve documentation also decreases their reliance on oral tradition, helping them scale more quickly.

## Engagement and Retention

### Invest in the Team You Have

**Employee happiness often depends on two factors:**
- Whether they know the impact of their work
- Whether they feel autonomy in the decisions they make every day

**Beyond this, successful teams need to:**
- Provide structure to keep team members engaged for the long term
- Actively listen to feedback
- Define clear paths for personal growth
- Train leaders to best support their teams

**After hiring and onboarding new employees, companies can either:**
- Focus on short-term output, OR
- Focus on the long-term productivity of their teams

**At high-growth companies:**
- Conditions change rapidly and early decisions can have lasting impact
- Even as it gets harder to remember how decisions were made in the first place
- Early employees can carry disproportionately more knowledge than new hires
- Be most effective at getting things done
- Be the company's greatest mentors through understanding both the technical context and how to navigate the organisation
- At the same time, they can start to feel overloaded or trapped in one part of the company or technical stack

**Key action:** Collaborate with your early employees to avoid this trap by building the right supporting structure for your team.

### Don't Mistake Productivity for Engagement

**The "surprise resignation" story:**

As an early manager at a previous company, Raylene was supporting a collaborative, highly productive team. One day, a long-tenured engineer arrived at their one-on-one and quietly handed her a letter of resignation. He'd been consistently delivering high-quality work, taking on challenging projects and even mentoring new hires and interns.

When she asked him why he was leaving, he said he no longer felt challenged – while he knew he was doing important work for the company, he couldn't see any way to both increase his impact and learn new skills.

**She now calls this the "surprise resignation"** – when people feel stuck in a local maximum and conclude it's easier to leave the company for an exciting opportunity rather than take on a new but seemingly less-impactful role within it.

**The realization:** While she hadn't noticed any warning signs, a simple conversation about his career aspirations would have revealed his concern.

**Key insight:** People stay engaged when they feel a personal sense of growth, and you can support this by looking beyond day-to-day productivity and asking the right questions.

**StripeSat survey:** Twice a year, they send out an employee survey called StripeSat to measure engagement. Key questions they ask:
- Do you have opportunities at work to learn and grow? What would you like to learn or get better at?
- Do you see yourself working at Stripe in three years? Why or why not?
- Do you believe there are good career opportunities at Stripe (e.g. stretch assignments, increased responsibility and internal mobility)? If not, what opportunities would excite you?

### Create Supported Paths for Mobility and Learning

**Helping people discover new opportunities and create independent projects** enables them to shape their story and role at the company. At Stripe, they create internal resources to advertise new teams, encourage employees to rotate onto new projects and run hackathons to foster creativity.

**Rotations:**
- People use rotations to learn a new language, explore a different part of their stack and in some cases permanently switch teams
- In the past six months, over a dozen engineers rotated between projects as disparate as iOS mobile development, core payment API features and machine learning applications
- They also highlight roles that would benefit most from internal transfers – for example, bootstrapping a new team or tackling a complex technical problem
- Highlighting these challenges helps direct longest-tenured engineers toward projects where they can provide the most help

**Hackathons:**
- Trying something new doesn't need to take weeks of planning or a new team
- They run internal hackathons to encourage building new tools and products
- At a recent hackathon, 80 people participated across multiple offices, and they shipped seven projects to both internal and external users, including right-to-left language support in Stripe Elements and internal tools for employee productivity

### Ask for Feedback and Respond to It

**As companies grow, responding to employee feedback requires both a scalable approach and listening carefully to individuals.** Employees recognise problems at companies all the time, but don't always know how to translate what they're seeing into effective change.

**They respond to employee feedback with three steps:**
1. Identify the problem
2. Design a way to collect structured feedback
3. Address the feedback; deliver the results

**Developer Experience survey example:**

Two years ago, engineers consistently described their development environment as slow and inefficient. To address this, they formed a team of experienced Stripe engineers focused on the internal developer experience. Despite their intuition and expertise, they had trouble identifying the most impactful projects.

**The team launched a Developer Experience survey** to guide their work, including questions such as:
- In the last week, how many hours did you lose due to problems with your development process?
- With our tools or infrastructure, what are one to two things we could do to make you more productive?
- In the codebase you work in, what's harder than it should be?

**Results:**
- The survey results showed them the most common request (by a factor of two!) was for a faster and more reliable edit-sync-test loop
- The team took this to heart and tackled a series of projects to improve the speed and reliability of syncing, reloading and testing code
- In the next round a few months later, results showed satisfaction in these areas had improved by 50–80%
- This created a positive feedback loop between the team and their users, and helped engineers feel heard

Since then, they've run Developer Experience surveys every quarter and continue to learn from the results.

## Wrapping Up

**As organisations evolve, how you scale your team has an enormous impact on your culture, productivity and employee engagement, and subsequently the success of the business.**

At quickly growing companies, conditions change rapidly, and what's working well today may not hold up tomorrow. While these practices have helped Stripe scale thus far, they'll continue iterating and develop new ones as they grow.

---

**Source:** [Scaling engineering organizations](https://stripe.com/in/guides/atlas/scaling-eng) by Raylene Yung, Stripe Atlas Guides

