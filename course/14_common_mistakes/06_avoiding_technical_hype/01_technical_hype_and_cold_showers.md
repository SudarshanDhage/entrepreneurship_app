# Technical Hype and Cold Showers

Reality checks on overhyped technical topics: when enthusiasm gets too far ahead of reality, and how to stay grounded in technical decision-making.

## The Premise

**It's great to get excited:** It's great when people get excited about things, but sometimes they get a little *too* excited. This is a collection of rigorous and respectful "cold showers" on overhyped topics. This does **not** mean the enthusiasm is bad or wrong: we're just reminding people to stay grounded.

**The danger for startups:** Following technical hype can lead to over-engineering, premature optimization, choosing complex solutions for problems you don't have, and wasting time and resources on technologies that don't actually solve your problems.

## Microservices: Please, Don't

**The hype:** "Microservices! Microservices!"

**The reality check:** Presents five fallacies of "why microservices solve problems monoliths have" and shows how either monoliths don't actually have those problems or that microservices make the problem even worse.

**The lesson:** Don't jump to microservices because they're trendy. Start with a monolith. Microservices solve scaling and organizational problems you likely don't have yet, while adding significant operational complexity.

**Caveats:** Abstract arguments and experience, no case studies or examples.

## Scalability! But at What COST?

**The hype:** "We need big data systems to handle big data."

**The reality check:** Benchmarking cutting-edge graph-processing algorithms running on 128-core clusters against a single-threaded 2014 Macbook Pro. The laptop consistently wins, sometimes by an order of magnitude.

**The lesson:** "If you are going to use a big data system for yourself, see if it is faster than your laptop. If you are going to build a big data system for others, see that it is faster than my laptop."

**Why this matters:** Many startups over-invest in distributed systems when a single server would suffice. Scale when you actually need to scale, not before.

**Caveats:** McSherry is really good at optimizing his algorithms and has skills the average data scientist does not. Big data systems might be better if you have ad-hoc queries and don't want to take the time to optimize them.

## Scaling SQLite to 4M QPS on a Single Server

**The hype:** "Scaling out is better than scaling up. Cloud is more scalable than bare metal."

**The reality check:** Expensify found that running a single bare-metal server was both faster and cheaper than using a x1e.32xlarge EC2 instance. By using one server, they could avoid sharding their data.

**The lesson:** Don't assume you need to scale out (horizontal scaling) or use cloud services. Sometimes a single powerful server is both faster and cheaper, especially when it avoids the complexity of sharding.

**Caveats:** Does not cover if scaling out bare metal has the same advantages over scaling out EC2 (assuming you can afford sharding). Can't really compare how much cheaper the bare metal is because they don't list the cost.

## Agile Methods: The Good, the Hype and the Ugly

**The hype:** "We should develop software using Agile."

**The reality check:** Review of all the different styles of Agile and how some of the practices (particularly replacing requirements with user stories and the lack of proper specification) are harmful in the long run.

**The lesson:** Agile is a good methodology, but it's imperfect. Some practices, particularly around requirements and specification, can cause problems. Don't adopt Agile dogma without thinking critically about what works for your context.

**Caveats:** While Meyer calls out some problems, overall he's very positive about Agile and recommends it as a good (but imperfect) methodology.

## VM Warmup Blows Hot and Cold

**The hype:** Your favourite programming language has been updated. The new version makes impressive performance improvement claims.

**The reality check:** Benchmarking modern programming languages under near-ideal circumstances, just for longer than before, suggests that we have not been benchmarking language implementations as accurately as we might wish. Many benchmarks slow down over time. Some never stabilise. Many benchmarking experiments will not be repeatable due to non-determinism. Warmup time is important, but is usually either ignored, or reported inaccurately.

**The lesson:** Don't trust performance claims without verifying them yourself in your specific context. Many language/framework performance improvements don't hold up under realistic conditions.

**Caveats:** Only evaluates the x86_64 architecture, and for only two operating systems (Linux and OpenBSD). Experiment conducted in 2017 (prior to meltdown patching). Evaluates mainly JITted language implementations (although C benchmarks were included).

## Web Framework Benchmarks

**The hype:** Anything about performance or scalability of various languages/web frameworks/databases.

**The reality check:** Actual hard data of various combinations of solutions under various tasks.

**The lesson:** When evaluating technologies, look for actual benchmark data rather than marketing claims. Raw performance numbers in isolation don't tell the whole story—you need to understand the context and trade-offs.

**Caveats:** Raw data you have to interpret yourself. Continually updating with new benchmarks. All implementations are public and you can improve them with a PR.

## Other Reality Checks

**Static vs Dynamic Typing:** A review of all the available literature (up to 2014), showing that the solid research is inconclusive about whether static typing reduces bugs. The conclusive research had methodological issues.

**Formal Verification:** Extensive literature review showing that formal methods are hard to learn, extremely expensive to apply, and often miss critical bugs. Additionally, researchers looked at three formally verified systems and found critical correctness bugs in all three.

**Identifier Naming:** Research shows no difference in debugging time or quality between abbreviated vs. full-word identifier names. Eye-tracking studies suggest underscore style may be processed faster than camelCase, but the research isn't definitive.

**Go Concurrency:** Despite claims that Go's concurrency system is easier to understand and less prone to bugs, an empirical study found plenty of concurrency-related bugs in popular Go software (Docker, Kubernetes, gRPC), with more than half caused by Go-specific problems.

## The Pattern

**Question the hype:** When everyone is excited about a new technology or approach, ask:
- Do we actually have the problem this solves?
- What's the actual evidence, not just marketing claims?
- What are the trade-offs and complexity costs?
- What would happen if we started simpler?

**Stay grounded:** The best technical decisions are based on:
- Understanding your actual problems
- Evidence, not hype
- Simplicity over complexity
- Incremental improvements over rewrites
- Measured results over benchmarks in isolation

## Key Takeaways

1. **Microservices often solve problems you don't have** - Start with a monolith.

2. **Big data systems may be slower than your laptop** - Measure before assuming you need distributed systems.

3. **Scaling out isn't always better** - Sometimes a single powerful server is faster and cheaper.

4. **Agile has problems too** - It's good but imperfect; don't adopt dogma uncritically.

5. **Performance claims need verification** - Benchmarks can be misleading; test in your context.

6. **Question all hype** - Even well-meaning enthusiasm can lead you astray.

7. **Start simple** - You can always add complexity later if you actually need it.

8. **Measure, don't assume** - Test actual solutions in your context before committing.

9. **Evidence over marketing** - Look for rigorous studies, not vendor claims.

10. **Complexity has costs** - Every new technology adds operational and cognitive overhead.

---

**Source:** [Awesome Cold Showers](https://github.com/hwayne/awesome-cold-showers), curated by Hillel Wayne. A rigorous and respectful curated list of "cold showers" on overhyped technical topics to help people stay grounded. The repository contains links to research papers, benchmarks, and analyses that challenge common assumptions about various technologies and practices.

