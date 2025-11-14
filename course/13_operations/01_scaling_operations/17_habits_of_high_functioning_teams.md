# Habits of High-Functioning Teams

What it actually looks like to be part of a high-performing software team, based on direct experience working with hundreds of developers. Four key habits: psychological safety, good hygiene practices, active redistribution of experience, and generous communication.

## The Challenge: What Does "Good" Look Like?

**The problem:** I often struggle to explain what it means to be part of a high-functioning software team. Sure, there are mountains of literature, and an entire genre of LinkedIn thought leadership that professes all kinds of guidelines and heuristics about what makes teams *work*, but in my experience, it's hard to internalize these ideas and follow someone else's model *if you've never seen what good looks like*.

**The experience:** I've been very lucky to have worked directly with dozens, if not hundreds, of developers by this point in my career. I've been on some unhealthy teams: teams where people were fearful, and held their cards very close to their chest out of a perceived or real worry around their job security. I've also been on dysfunctional teams, where many days or weeks of development time was wasted while the team whiplashed between unclear priorities, or where the cost of coordination had grown so high that no one simply wanted to do it, leaving team as a collective of individuals rather than a unit.

**The contrast:** But I've luckily spent time on some very high-performing teams. When I've been on those teams, I was excited to come to work everyday, I wasn't afraid of disagreeing publicly with those more senior than me, and I felt like my voice and my work had impact.

## 1. High Psychological Safety

**The concept:** Psychological safety has been around as a concept for a while, so I'm not really going to spend much time explaining it. Read this first if you haven't previously encountered the concept.

**It's deeper than training:** Software teams are staffed by real people who operate within invisible social and political structures, who are socialized from birth to be more assertive, more deferential, more outspoken, more polite, more argumentative, more placating, and so on. I say these obvious platitudes to make a point that psychological safety isn't just about hiring some consultants to run employee trainings about what the concept means: Creating true psychological safety requires leaders and managers to take stock of all of the invisible, socialized rules of engagement between people, and understand how those affect one's ability to meaningfully participate in team discussions and dynamics.

**Social privilege matters:** In short: social privilege is a Big Thing. Otherwise, don't be surprised if little things that eat away at team cohesion start manifesting: microaggressions, stereotype threat, the encoding of survivorship bias into your beliefs about what makes an effective team member.

### Observable Behaviors of High Psychological Safety

**Regular retrospectives with real issues:**
- Regular retrospectives, with a reasonable number of items in the "what's not going well?" column. It shouldn't look like sunshine and rainbows all the time. That would actually make me question whether difficult topics are being raised in retros. Healthy teams should be able to openly introspect and self-critique, because everyone understands that constructive feedback is in the service of continuous improvement.

**Struggle timebox:**
- Individuals don't spend a lot of time being stuck or blocked on a problem. There's an explicit or implicit "struggle timebox", after which time, they'll ask for help from a peer, and know that they won't be judged negatively for doing so.

**Value separated from output:**
- Individuals dissociate their **value** to the team from their visible **output**. I've seen some cases where people felt frustrated that their lines of code were later removed or refactored. On healthy teams, people embrace the fact that improvement happens incrementally and constantly, and their contribution is to the overall team's outcomes, not to specific outputs like lines or code. It's an expression of "Here's what we delivered", versus "Here's what I delivered". Also, safe teams can have conversations about what value means, and how it's not just lines of code.

**More PTO and sick time:**
- People tend to take more PTO and sick time, interestingly. I believe that this is a symptom of their belief that the rest of the team will continue to make the correct decisions in their absence, because enough conversations have happened, which enables the entire team to feel aligned on product and technical decisions. But I'm less sure about causality on this. People can also take more PTO if they're really burned out.

### Process Experiments: Feedback Week

**The opportunity:** When a team has a high degree of psychological safety, there are really cool process experiments that you can try, that I believe to generate a self-reinforcing positive feedback cycle that creates even higher levels of trust and safety.

**The experiment:** On my first high-performing team, during one of our retros, everyone felt like the twice-yearly performance review cycle, where our managers gathered feedback from our peers, wasn't frequent or granular enough to promote career growth, especially when our team's priorities were evolving so quickly. So, I proposed an experiment:

**Feedback Week.**

It's a one-week process, where everyone (including the team lead and PM) is randomly assigned to collect feedback for another person. It went so well, that after my teammates went to new teams, they brought the experiment with them. And eventually, other teams in the office started copying us!

**The indicator:** The ability to run something like Feedback Week is an indicator that your team is in a place of high psychological safety. If you're lucky enough to be there, my advice is: don't just stand still. This is an opportunity to boldly experiment with your processes and practices, and try things like Feedback Week, that can help you tap into hidden positive feedback loops.

## 2. Good Hygiene Practices

**Woods Theorem:** *As the complexity of a system increases, the accuracy of any single agent's own model of that system decreases rapidly.*

**The reality:** I'll just straight up admit that I will never have a comprehensive mental model of the GitHub monolith. It's too big, has too many logical paths, and frankly, it won't make me better at my job to sink an inordinate amount of time in learning all the parts of the code. Plus, it'll just change tomorrow.

**The reliance on artifacts:** So, when I do have to gather enough context so I can implement the next feature or bug fix, I rely on the presence and accuracy of artifacts in the code, left by those who worked on it before me.

**The spelunking:** I spend a lot my time doing this sort of spelunking through code: running `git blame`, looking at past commits, linked issues, and anything that can help tell me *why* a certain line of code was written that way. A productivity killer is when I see a mysterious diff, and the commit message: "WIP".

### What Good Hygiene Means

**The principle:** Good software development hygiene means **taking a bit of extra time to record present-day context**. This can take the form of:

**Descriptive commit messages:**
- At minimum, every commit message contains a verb. Some teams go even further and require that the issue number is tracked in every commit. Choose the level of cognitive investment that works for your team.

**Intention-revealing names:**
- Intention-revealing class names and method names that follow language and framework conventions

**Helpful tests:**
- Unit tests with helpful descriptions, that use realistic variable names and data, and not "foo" and "bar" for variables

**Context in tracking issues:**
- Keeping all back-and-forth communication about the feature inside the tracking issue, and not in Slack DMs and other places where it's not possible for your new team member in 6 months from now to access

### It's About Empathy

**Empathy for teammates:** Ultimately, following good hygiene practices is about empathy. Cleaner artifacts means that your teammates can absorb context more quickly and spend less cognitive energy on context-switching and spelunking.

**Empathy for future self:** But also, it pays to empathize with *your future self*. There's an entire branch of moral philosophy that says that Future You is a distinct entity who has moral rights claims (and that's why eating that extra tub of Ben & Jerry's or taking up drag racing today for present-day hedonistic delight might be a morally dubious action) but without getting too deeply into that, I'll just say: Investments in socializing these hygiene habits early on will pay off later, particularly if you're paged at 3am one morning because of a line of code you wrote!

## 3. Active Redistribution of "Experience Points"

**The RPG analogy:** If you've ever had a conversation with me about video games, you'll know that I LOVE role-playing games. Especially the ones in the Fire Emblem and Pokemon franchises. I'm slowly getting caught up with the Final Fantasy games, too!

**The parallel:** I'm saying this because I think there are a lot of parallels between how I build my armies within Fire Emblem, and how I think about building well-balanced software development teams. In RPGs, when I have my core team, I really like trying to level up all my characters evenly. If I gain a new character at a lower level, but she has a skillset or affinity that complements the rest of my team, I'll invest in leveling her up a bit so she can move around the map with a little less worry about enemy attacks. And if I have a character that's at a super high level to begin with, I avoid putting them into combat with weaker enemies, because they'll just hog experience points that will benefit my low- and mid-level fighters more.

**The principle in software:** I like to think that a similar principle is true in software teams, but instead of experience points that build strength, defense, magic, and resistance, every new piece of work is an "enemy" that, when delivered, will spread domain context and confidence around your team.

**No central tactician:** There is often no central "tactician" role on a team, though — which is where this metaphor starts to fall apart (managers and PMs don't count — they usually won't have enough visibility, or up-to-date context, and anyway, it's a bad idea to centralize something so complex and dynamic on one person).

**Don't always deploy senior developers:** If your team already has a lot of Great Knights and Paladins — err, I mean, senior developers, as a group, you should make a point to not constantly deploy only them to tackle difficult stories. On healthy teams, it's also part of their job to engage in context redistribution, so that a less experienced fighter — I mean, engineer — can gain some valuable experience points too.

**The benefit:** It raises the productivity and morale of the entire team if everyone feels like they're at least somewhat equipped to tackle any challenge that comes their way. And if not, they know that they can always add a Falcon Knight as an adjutant — in other words, ask for help from the more experienced folks.

## 4. Communicating Generously

**The robustness principle:** I've thought a lot about this last point. Of all the ways that other people have said what's in my brain, I think best of all, I like how Nat Friedman put it in a recent all-hands. He said something like, "Our communications with each other should be guided by the robustness principle: Be conservative in what you send, be liberal in what you accept." He went on to encourage us to adhere to the principle of charity, especially when communicating with each other during the very difficult current circumstances. But I think this principle is followed 100% of the time on high-performing teams.

**The mentor training framing:** I really like this framing, because it reminds me of a mentor training that I went through many years ago when I was a volunteer at codebar. "Assume that every student you interact with has limited information, but infinite intelligence." That places the onus squarely on the shoulders of the mentor to make sure that their explanations make sense — which, given the inherent imbalance of power between a teacher and a learner, is a fine way to distribute the extra emotional labor.

### What Generous Communication Means

**Generous communication between peers means that at all times, we assume that anyone asking a question:**

- Has done the basic research, e.g. they've googled the thing already
- Is asking a human, because they've been unable to find their answer in any written-down place. Because that written-down place is difficult to find, or it doesn't exist yet.

**The assumption:** In other words: assume your peer is a competent, intelligent, reasonable person who is asking a question because they're lacking context, that they've already attempted to procure on their own.

**The frustration:** I'm not sure I can express in words how frustrating it is to have your context and experience "rounded down" constantly, when you start asking for help. Yes, there is a gendered element to this — but that's beyond the scope of this discussion for now. In the past, I've written multiple tweet threads about how demoralizing it is for another person to assume that you're far less experienced and knowledgeable than you really are. Of course, there's no way for the other person to really know — omniscience is, *of course*, an impossible ask! But, there's a middle ground here, which is reasonable to ask: generosity.

### Examples: Lack of Generosity vs. Generosity

**Lack of generosity:**
> Me: Hey, why is there a load balancer here?
> 
> X: Load balancers are used to spread requests over multiple services so we don't get DDoS'd! Here are some articles on the basics of load balancers and why we might theoretically use them!
> 
> Me: OK but that wasn't my question. I know what load balancers are. I just want to know about the architecture decision for putting HAproxy, in front of this particular service.
> 
> X: Oh! Well, you should've just asked it that way! 😤

**Generosity:**
> Me: Hey, why is there a load balancer here?
> 
> X: I'm guessing that you're asking for context about why we chose HAproxy, and why these services in particular. Stop me now if that's wrong.
> 
> Me: No, that's correct! Thanks for checking first.
> 
> X: Sure. So, when we built this system 18 months ago……….

**The key difference:** The key difference in these interactions is that in the generous interaction, the answerer checked their assumptions about the question, and by extension, the asker's context level and intention, before plowing into an answer.

**The positive impacts:** There are hugely positive impacts of interacting in a generous way: first, notice how there are fewer words exchanged? They actually got to the solution faster. Secondly, there was no unnecessary friction generated. Both people are united in slaying the dragon of uncertainty; rather than getting bogged in jousting over how much each person knows, and walking away with perhaps the answer, but some trust and goodwill lost.

## Key Takeaways

1. **High psychological safety enables process experiments** - When teams have high safety, they can try things like Feedback Week that create positive feedback loops.

2. **Psychological safety goes deeper than training** - Requires understanding invisible social structures, social privilege, and how they affect participation.

3. **Observable behaviors of safe teams** - Regular retros with real issues, struggle timeboxes, value separated from output, more PTO.

4. **Good hygiene is empathy** - Taking extra time to document context is empathy for teammates and your future self.

5. **Hygiene practices** - Descriptive commits, intention-revealing names, helpful tests, context in tracking issues.

6. **Redistribute "experience points"** - Don't always give difficult work to senior developers. Help less experienced team members level up.

7. **No central tactician** - Context redistribution shouldn't be centralized on one person (manager/PM).

8. **Communicate generously** - Assume competence: "limited information, infinite intelligence."

9. **Check assumptions first** - Before answering, check what the person is actually asking. This saves time and preserves trust.

10. **Generosity creates positive cycles** - Generous communication reduces friction, builds trust, and gets to solutions faster.

---

**Source:** [Habits of High-Functioning Teams](https://deniseyu.io/2020/05/23/habits-of-high-performing-teams.html), deniseyu.io by Denise Yu (May 23, 2020). Denise Yu is an engineer and sketchnoter who has worked directly with hundreds of developers and documented characteristics of high-performing teams based on direct experience.

