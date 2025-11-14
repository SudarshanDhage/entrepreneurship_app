# Build vs Buy: Experimentation Platforms

Should you build an in-house experimentation service or buy/rent one from an external provider? Understanding the costs, infrastructure requirements, and trade-offs.

## The Core Decision

**The context:** Companies like Bing, Google, and LinkedIn increased the number of product experiments they ran by an order of magnitude after they built an experimentation platform. Today, these companies run tens of thousands of experiments every year. While these large technology companies have dedicated teams that build and maintain their own experimentation platforms, you must decide whether to build or buy based on the context of your business.

**Two key questions to help you decide:**
1. What would it cost to build your own platform?
2. What can an external platform deliver?

## Building Your Own

**The goal:** An experimentation platform should enable fast product iteration based on data-driven metrics. Ideally it should be self-serve so as to enable your teams to make ship decisions without relying on a central committee; and in the process, minimize the costs of running experiments.

**Building such a platform requires investment in three key areas:**
1. Reliable core infrastructure to control and execute experiments
2. An analysis framework to make sense of the data and thereby product decisions
3. A set of software development kits (SDKs) and tools to integrate with the company's existing software development and decision-making processes

### Core Infrastructure

**The foundation:** The core infrastructure is the foundation of the experimentation platform. It should be reliable, always available and must be fast. You won't want your experimentation platform to introduce any variance, or worse, negatively affect the product's experience.

**Four key components:**

**1. Experiment Control**
- Persists and validates the specifications for each experiment including any subsequent iterations
- Each experiment specifies several parameters such as start and end dates, control and variants, target users, sample sizes, and related configuration
- Enforces approval workflows as well as roles and permissions to ensure that only approved experiments are allowed to run
- Ensures only authorized team members can start and stop an experiment

**2. Variant Assignment**
- Given a user request, this component decides how to assign the request to a variant in an experiment
- Assignment is based on the experiment specification and a pseudo-random hash of an identifier

**Important considerations:**
- Ensuring random but deterministic assignment of users to control and variant buckets (you don't want your users to switch between experiences)
- Assigning users across multiple concurrent experiments while ensuring a consistent experience, and when needed, keep experiments isolated, so that one user is not simultaneously in multiple conflicting experiments
- Delivering assignments without incurring additional latency or hurting application availability

**3. Data Processing**
- Delivering reliable and automated data processing is critical to establish organizational trust in experiment results
- To get data into a reliable state, you would need to:
  - Consolidate, sort, and join the logs from different sources
  - Cleanse and enrich these logs where necessary
  - Compute all the metrics for various segments and user dimensions
  - Calculate p-values and confidence intervals

**Critical validation:** This part is critical, and you would want to run a series of A/A tests to ensure correctness. Finally, we must run basic health checks to ensure correctness.

**4. Experiment Analysis**
- Any good experimentation platform should enable every person in the team to easily read and interpret their experiment results
- This is where the rubber hits the road; this is what separates a valuable platform from one that'll be discarded quickly

**Essential features:**
- Results should be clear and concise, highlighting the relative change in metrics along with clear signals about statistical significance
- Must provide confidence intervals (platforms that don't are at best amusing, and at worst misleading and damaging to your product)
- Should reveal all relevant metrics, not just the one that the experiment was tailored for
- Results should enable slicing across user dimensions and segments
- Should use lower p-values to filter for the most significant metrics
- The team should also be able to see per metric views of all experiment results to see which experiments are most impactful

### APIs and SDKs

**The integration layer:** All of the experiment configurations would need to reach your applications, and this is done via APIs and SDKs.

**Common considerations:**
- Support for different points of production decisioning which could be on the client side or server-side
- Support for all languages that various teams may choose for their respective functional goals
- SDKs should be resilient to network flakiness
- API versioning should be carefully considered with existing SDK usage

## Buying/Renting

**Key considerations when choosing an external service:**

**1. Core Functionality**
- Does the service deliver the functionality you need for your application?
- Is the service optimized for front-end or back-end experimentation?
- Does it work for both web and mobile applications?
- Does the nice drag-and-drop editor work well for web, but does the mobile SDK crash a lot?

**2. SDK Support**
- Does the service support the SDK in the language you need?

**3. Performance**
- Do SDK calls slow down the application?

**4. Data Ingestion**
- Can the service ingest data from different sources to avoid logging data with multiple services and to join the data for a richer analysis?

**5. Near Real-time Results**
- Do you need near-real time results to quickly detect and stop bad experiments?

**6. Randomization Unit**
- Does the service allow randomization units such as sessions or workspaces in addition to users?

**7. Metrics**
- Does the service compute all the metrics required to make a sound decision?
- Do these computed metrics reconcile with other sources in the company?

**8. Health & Audit**
- Does the service automatically surface health and system metrics to proactively identify issues?
- Does the service provide approval workflows to implement team reviews?
- Does it provide an audit log of changes?

**9. Access Control**
- Does the service allow you to control who has permissions to start and stop experiments?

## Building vs. Buying: Total Cost of Ownership

**The framework:** To set yourself up for success, estimate how many experiments your organization would run assuming everyone in the company truly embraces experimentation. As the number of experiments scales, the experimentation infrastructure can become increasingly complex to manage and support.

**To decide between building vs. buying, consider:**
- Total cost of ownership (TCO) for building in-house
- Opportunity cost of building an experimentation platform in-house
- Compare this against your functional needs, reliability, scalability, and costs of using an external service

### Total Cost of Ownership

**To estimate the TCO for an in-house platform, consider the costs for:**

**1. Development**
- Requires top-notch infrastructure engineers to build the core infrastructure that offers both high availability and high performance
- Requires dedicated data scientists and data engineers to ensure that data processing, computations, and results are reliable and trustworthy

**2. Operations & Support**
- To provide uptime SLAs, this team needs to devote a part of its time to on-call rotation
- This team also needs to support inquiries and support tickets from all users in the company

**3. Infrastructure**
- The core infrastructure must be redundant and resilient with automated scaling built-in to deliver a stable and trusted service
- Be sure to include essential monitoring and operational tooling to estimate your infrastructure operating costs
- If you require near-real time results, the complexity and cost of this infrastructure can increase further

**4. SDKs for Everyone**
- Each team running experiments requires client and/or server SDKs in their own preferred language
- The platform team needs to include engineers familiar with the nuances of these languages to build and support the required SDKs over time

## Opportunity Cost

**The trade-off:** Building an in-house platform comes at the expense of engineers and dollars that you could invest in your core product and functionality that your users want.

**The risk:** A good experimentation platform is a powerhouse that accelerates your pace of innovation. If it slows down your client teams, they won't use it and your initial investment may turn out to be a waste. If you do decide to build your own, you must invest in the team, infrastructure, and SDKs to stay ahead of the needs of all client teams in your organization.

**The external service advantage:** As a point of comparison, assuming an external service meets your functional requirements, buying may offer a faster pace of innovation than an in-house platform. The external service is usually committed to innovating on behalf of all their customers and setting the industry standard for common requirements such as scalability, performance, security, and governance. This means you enjoy the leading pace of innovation in experimentation by default.

**When building might still be better:** There are some cases where building could still be better than buying if external services don't meet your functional requirements. For example, if you run software deeply integrated with hardware, such as Roku, you may want a unique or customized way to deploy and control your experiments.

## Summary

**The bottom line:** An external service can help you focus on driving the car rather than assembling all the parts of an experimentation platform.

**Recommendation:** To enjoy the most flexibility, consider a service with a free tier and easy onboarding to see the value of simple A/B tests without committing to any contracts. **Get your hands on something that works on day one, and most importantly provides transparent pricing so you only get what you need.**

## Key Takeaways

1. **Large companies run tens of thousands of experiments per year** - but they have dedicated teams building and maintaining platforms.

2. **Building requires investment in three areas:** Core infrastructure, analysis framework, and APIs/SDKs.

3. **Core infrastructure has four components:** Experiment control, variant assignment, data processing, and experiment analysis.

4. **Consider TCO:** Development costs, operations & support, infrastructure costs, and SDK maintenance for all languages your teams need.

5. **Consider opportunity cost:** Engineers building experimentation infrastructure aren't building your core product.

6. **External services offer faster innovation:** They innovate on behalf of all customers and set industry standards.

7. **Start with external services:** Try a service with a free tier and transparent pricing before committing to building your own.

8. **Build only if external services don't meet functional requirements:** For example, deeply integrated hardware/software may need custom solutions.

---

**Source:** [Build vs Buy](https://www.statsig.com/articles/build-vs-buy), Statsig. Statsig provides experimentation platforms and product analytics tools.

