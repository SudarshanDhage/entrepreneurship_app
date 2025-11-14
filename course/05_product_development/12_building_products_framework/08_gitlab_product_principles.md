# GitLab Product Principles

Core principles for building world-class products through customer-centric innovation. These principles guide GitLab's product development practice with the customers' voice at the core.

## Our Product Principles

Everything we do is for our customers, and we are only successful when they succeed in delivering secure software faster to their customers and internal users.

### 1. We are customer zero, therefore we use our own product

Everything you put into the product should be a feature you or the Engineering team would use as part of daily work. If the answer is no, then challenge your "why," as there might be a better solution that will have a bigger impact for customers.

### 2. We are not our only customer

Meet with customers as much as possible as everything we do is for them. It is tempting to assume that we understand our customers through our own usage and dogfooding, but that only gets you so far and we can be wrong. Validate assumptions through strategic user research, customer interviews, and feedback sessions.

### 3. We are design-led

It does not matter what customer pain points you work with Engineering to resolve if what is provided to customers is hard (or almost impossible) to use. User experience is our top priority as we have a very technical product, however it should be easy enough for someone new to DevSecOps to get started quickly. This includes everything from onboarding to shipping secure software leveraging GitLab.

### 4. We value quality over velocity

Delivering incomplete features and capabilities to ensure your team achieves a defined velocity is not acceptable. Everything we ship to customers must be:
- User validated
- Bug free
- Not introduce security vulnerabilities
- Be able to achieve GitLab.com scale
- Include documentation
- Be available on all customer deployment choices simultaneously

Accruing additional technical debt in favor of velocity is also not acceptable as this leads to future quality issues around availability, scalability, reliability, and security.

### 5. We value data over intuition and anecdotes

Everything we build must have success metrics we can track to ensure we are providing value to customers. We measure outcomes, not launches, and this is only possible with experimentation and proper instrumentation. All features must be instrumented so success metrics can be tracked and adjustments to plans can be made through product usage.

### 6. We fail fast and iterate with intention

Define a hypothesis on how to address a customer use case or pain point and validate (or invalidate) it quickly through problem validation. Take the outcome of the problem validation cycle and build an iteration strategy to deliver it with a focus on usability and quality. Revalidate your hypothesis through solution validation with each iteration so you can adjust plans as needed.

Problem and solution validation ensures the customer voice is key in making decisions.

### 7. We believe in product-led growth over unguided experiences

Our product should be GitLab's best Sales team member, and its own biggest champion. Enable feature discovery moments to let customers know there is more value based on their usage, actions taken, or configuration choices. The more customers adopt our product's capabilities, the more return on investment they experience, which builds more internal GitLab champions.

### 8. We like to win…and we only win as a team

We win when our customers are able to successfully ship secure software faster with GitLab. This requires us to hold ourselves to the highest levels of execution and collaboration within Product across our Product Management, UX Research, Product Design, and Technical Writing teams. While teamwork within Product is necessary, it is also not sufficient. We require that same standard of execution and collaboration with our cross-functional team members across R&D and GTM.

## The Minimal Valuable Change (MVC)

**Minimal Valuable Change (MVC)** is the GitLab path to delivering the smallest measurable improvement for users, customers, and the wider community.

**Our approach requires four pillars:**

1. **Relentless customer focus and commitment** to understanding their workflows, using research and validation
2. **Measurable outcomes** that use established metrics for success in tracking adoption, usage, or other business outcomes
3. **Product functionality** that adheres to GA criteria listed in the levels of support
4. **Future vision** to expand the MVC beyond the initial release

### MVC Guidelines

When considering how to scope a feature for a release, remember that it is not ok to ship an "incomplete" feature to customers. MVC means reducing the scope so we can ship quickly. It doesn't mean shipping something that hurts the usability of GitLab.

**First impressions are important.** A feature that does not offer enough value or hinders the user experience may have a negative effect that discourages users from trying that feature again in the future.

If there are obvious gaps in your MVC or you can anticipate follow-up requests, consider whether your feature is complete enough to be released to users.

If you are unsure whether your feature is complete enough to be an MVC, you can use approaches such as:
- Dogfooding
- Beta programs
- Feature flags
- User research

### MVC Examples

1. **Ship a feature through the API and not the UI** — Build a GraphQL endpoint for deleting attachment from a project before building the UI
2. **Exposing a minimal set of functionality** — Add a basic read-only page displaying queued jobs, with more capabilities added in subsequent releases

### When MVC is Not Advised

MVC approach is not advised when changing core parts of the experience. An example of a core experience is comments. When building this out for work items, they waited to release the new feature to end users until they reached parity with comments in Issues and MRs.

## Iteration

An MVC approach is a byproduct of our spirit of iteration. That means we break problems down as small as possible, and focus on reduced cycle time. Thinking iteratively is not always intuitive, and breaking certain topics or projects down can be challenging.

**Iteration speed and product excellence:**

To ensure that our efforts consistently deliver value to users, each iteration must:
1. **Define Expected Impact:** Clearly articulate the expected measurable positive impact of the iteration on users
2. **Establish Metrics for Success:** Identify specific metrics that will be used to evaluate the success of the iteration before declaring the feature GA

Success of an initiative is not measured by the deployment of a change or the completion of an iteration. True success is determined by whether the iteration achieved its predefined objectives, as evidenced by tangible business and product metrics.

## Subtractive Thinking

Humans tend to favor solutions that add features than solutions that remove them, even when removing features is more efficient—great PMs recognize this bias and utilize subtractive thinking to create great user experiences.

Customers will tell us when we're missing something they need, but they're unlikely to explicitly tell us when we're overwhelming them with unwanted features.

## Convention over Configuration

We understand that a natural inclination when using application development tools is to create an array of buttons to press and knobs to turn. We believe, however, that adding options to an application does not necessarily improve the user's experience of that application. The best way to serve our users is to create an application that reduces complexity while still offering the features they need.

**When considering adding new configuration:**

- **Ensure a great experience by default** — GitLab should work perfectly right out of the box for most users
- **GitLab.com values should be the default** — the settings used on GitLab.com should be the defaults for self-managed
- **Encourage favorable behaviors by limiting configuration** — Convention implies that we're encouraging customers to do things in a certain way
- **Design for users not intermediaries** — Avoid building a product that administrators love because it is configurable, but developers hate because it is overly complex

**Working by Default:**

From the perspective of someone using GitLab, the feature does not exist until it works by default. This means, with few exceptions, features should simply work on GitLab.com and self-managed installations without setup, toggling feature flags, modifying configurations, or installing extra components.

"Enabled by default" ≠ "Working by default." Working by default requires:
- **Enabled-by-default** — it must not require modifying configurations, installing extra components, or be behind a feature flag
- **Setup-by-default** — it should not require setup before the feature can be used

**Avoid Limits:** Limits should be in place to protect the system but not to "slowly try out" a feature. By limiting the usefulness of a feature right from the start, you are only limiting its adoption and usefulness.

**Avoid configuration completely when possible:** Requests for configuration can be a proxy for trying to support a fragile workflow. Rather than enabling bad habits and incurring product debt, effort should be spent helping customers adopt best practices.

**Configuration Principles:**
- Configuration builds up over time — Every configuration option multiplies complexity
- Configuration is hard to remove — Removing a configuration after it ships is much more work than not introducing it
- Configuration is an expensive testing mechanism — Adding a configuration is a one-way door that should be avoided if possible. Consider using feature flags instead.

## Avoid "Not Invented Here" Syndrome

Just because something is not invented here doesn't mean it doesn't have a perfect home within our solution. Leveraging existing technology allows us to:
- Get to market much more quickly
- Contribute to Open Source (and help strengthen Open Source as a whole)
- Focus our own people on making GitLab itself better

Building professional relationships with tool creators also benefits GitLab since they may have important user perspectives around your categories.

**Success examples:**
- Code Quality in CI/CD pipelines by embedding CodeClimate
- Feature Flags by using the Unleash client library
- Mobile publishing by utilizing FastLane with GitLab

## Integrate Other Applications Thoughtfully

While a single application is the best approach, multiple applications that work well together is better than ones that don't.

**Key guidelines:**
- **Don't clone everything** — Focus efforts on places where we can deliver value by helping bridge the gap between two applications
- **Prevent broken workflows for free** — Features and UX that might break a customer's workflow should be offered freely
- **Charge for adding value to an interaction** — When GitLab adds unique value that external features couldn't otherwise have
- **Consider the right buyer for pricing** — Organizational requirement integrations (multiple teams) vs. extending GitLab capabilities (end-user)
- **Respect security and permissions** — External applications may have security and permissions concerns we don't have
- **Use empty states for feature discovery** — If someone is not using the GitLab feature and also not integrating their tool of choice, that's the worst possible experience
- **Use our own design language** — Keep design cohesive across the application
- **Be transparent about the data source** — Make it clear when data comes from elsewhere

**Avoid plugins and commercial marketplaces:**

Because GitLab is an open core product, third parties can add functionality directly to GitLab. Adding directly to the GitLab codebase (as opposed to building a plugin) has significant advantages:

**For users:**
- They are more likely to use this functionality because it's distributed to all users by default
- The functionality always works out of the box, requiring no additional software
- Users don't have to search for what plugins are available, or test multiple options
- Administrators never have to avoid an upgrade for fear that it might break an important plugin

**For developers:**
- Their work isn't limited in functionality because they're changing the code of the product itself
- Their code will be tested along with the rest of the product
- Community effort is not wasted on developing multiple plugins that all do the same thing
- Developers don't have to sacrifice velocity in favor of predictability

## Product and Feature Naming

### Give products and features descriptive, not distinctive, names

GitLab is a DevOps Platform, not a collection of DevOps point solutions. Descriptive names are:
- **Efficient** — Generally not eligible for trademark registration, avoiding time, effort, and expense
- **Inclusive** — Most accessible to a global audience because they can be directly translated into other languages

As an example, `CI/CD Components Library` is a descriptive name while `CI/CD ATOM` is a distinctive name.

### Use prepositions when referring to third-party products

When naming a GitLab extension, plugin, app, or integration for a third-party product, either include the third-party service name with a preposition like `for`, or don't include it at all. For example, `GitLab.com for Jira Cloud`.

## Next Generation Principles

### Modern first

When developing features to compete with existing competitors, make sure to solve problems for modern development teams first, and then see what's missing for legacy teams. Modern first does not mean non-modern never. It means that we should first learn how teams are using the feature in a modern way, and then see what's missing.

### Developer first

Our strategy includes going after many new personas, but when developing features in these new areas, it's important to remember to start with the developer. If we can make security great for developers and then great for security professionals, we'll be much more successful.

### Cloud-native first

We build features for cloud-native first, and then support the rest. This allows us to focus on where development is going, and deliver solutions that every company aspires to use eventually.

### Prioritize current adopters

By focusing on next-generation development flows, we build features where our initial users are early adopters. We optimize GitLab to support the larger number of current and future adopters of next-generation principles. This will come at the cost of sustained investment in initial workflows for early adopters.

## User Experience Principles

A highly usable interface with cohesive workflows and comprehensive documentation is a must to stay ahead of best-in-class competitors.

**General user experience principles:**
- **Strive for simplicity** — Using GitLab should be easy. Users should think about the applications they are building, not how to make our app work
- **Depth over breadth** — A world-class experience requires deep, powerful, useful features. We must also identify capabilities that can be deprecated
- **Better than before** — Our MVC principle pushes back against the notion that something must be better than nothing. Instead, we assess if the user experience is better than before
- **Timeless design** — The user experience should be relevant both today and years from now. Ask yourself, "How would we build something if we knew this was the last time a team could touch it?"

## Be Ambitious

Many crazy, over-ambitious ideas sound like they are impossible just because no one else is doing them. Since we have amazing engineers and a culture of shipping minimal valuable changes, we are able to accomplish many more "impossible" things than other organizations.

We don't want to shy away from challenging ourselves and always want to keep a sense of urgency. Aiming for more helps us do that. We arrived at our preference for ambitious planning after measuring our velocity and finding that our velocity was unchanged whether we scheduled ambitiously or scheduled for providing slack.

## Drive Product Usage

Users can only experience GitLab's value when they actively use the product features. Therefore the Product team's mission isn't only shipping features and building products, but also driving usage and delivering value.

**Two frameworks:**
1. **AARRR framework** (Acquisition, Activation, Retention, Revenue, Referral) — Think about how to drive a single feature's usage
2. **Customer Adoption Journey** — Think about cross-adoption of product features

**The Golden Journey:** The most common stages adopted by paid customers: Create → Plan → Verify → Release. Our biggest opportunity is to improve Verify to Release adoption rate.

## Flow One

Shipping only MVCs can result in a large set of loosely connected pieces that don't necessarily combine into a single, great user experience.

**Flow One offers an alternative:** You draw out a workflow consisting of MVCs (that can be shipped individually). The workflow should only cover a specific, narrow use-case, and nothing more.

This means you:
- Avoid creating an inflexible, long-term plan
- Can more easily construct a full feature/capability, which is more easily marketed
- Can provide context to each individual change ("we need this as part of X")
- Can continue to ship MVCs
- Work concurrently on several items, none of which are blocking

## Additional Principles

### Avoid enforced workflows but allow enterprise flexibility

Enforced workflows should be avoided in GitLab. They restrict GitLab to a smaller number of use cases, reduce value, require overhead to maintain, and can stifle teams. We should trust our users to use GitLab responsibly, giving them freedom.

However, there are organizations that rely on enforced workflows for a variety of reasons. We should consider allowing some enforcement at the group level to balance team efficiency and organizational policy, but default them off.

### Prefer small primitives

Small primitives are building blocks in GitLab. They are an abstraction not at the technical level, but truly at the product level. Small primitives can be combined, built-upon further, and otherwise leveraged to create new functionality.

They are especially powerful because they usually take less effort and provide higher leverage than you would get from a more "complete" but standalone feature. Think of how simple Unix command line utilities can be chained together to do really complicated things.

### Every feature is owned by a group

Features should be owned by one group, including the respective DRIs of that group. Unowned product features are unsupervised and continue to accrue technical debt over time, which increases the risk of performance and maintenance issues.

### Always allow for deploying to production

Sometimes fast deployments are needed to fix a service or application outage. Controls that prevent changes from reaching Production are okay as safeguards, but they should be able to be quickly removed or disabled if necessary.

### Data-driven work

Using data to learn from our users is important. We should:
- Build and use tools that work for both GitLab.com and self-managed
- Start from a question, and build/collect what we need to answer that question
- Use and improve existing tools we have inside of GitLab before leaning towards off-the-shelf products
- Make things that help customers, sales team, and customer success teams

---

**Source:** [Product Principles](https://handbook.gitlab.com/handbook/product/product-principles/) - GitLab Handbook

