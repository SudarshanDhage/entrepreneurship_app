# Experiments at Airbnb

**"Controlled experiments are a great way to inform decisions around product development."**

Airbnb uses controlled experiments to learn and make decisions at every step of product development, from design to algorithms. While the basic principles behind controlled experiments are relatively straightforward, using experiments in a complex online ecosystem during fast-paced product development can lead to a number of common pitfalls.

## Why Experiments?

Experiments provide a clean and simple way to make **causal inference**. It's often surprisingly hard to tell the impact of something you do by simply doing it and seeing what happens.

The outside world often has a much larger effect on metrics than product changes do. Users can behave very differently depending on:
- The day of week
- The time of year
- The weather (especially in the case of a travel company like Airbnb)
- Whether they learned about the website through an online ad or found the site organically

**Controlled experiments isolate the impact of the product change while controlling for these external factors.**

When you test a single change, the methodology is often called **A/B testing** or **split testing**.

## The Case of Airbnb

At Airbnb, they built their own A/B testing framework because their business has features that make experimentation more involved than a regular change of a button color:

1. Users can browse when not logged in or signed up, making it more difficult to tie a user to actions
2. People often switch devices (between web and mobile) in the midst of booking
3. Bookings can take a few days to confirm, so they need to wait for those results
4. Successful bookings are often dependent on available inventory and responsiveness of hosts — factors out of their control

The booking flow is complex: search → contact host → host accepts → guest books. They look at the process of going through these stages, but the overall conversion rate between searching and booking is the main metric.

## How Long Do You Need to Run an Experiment?

**A very common source of confusion in online controlled experiments is how much time you need to make a conclusion about the results.**

### The Problem with Stopping Too Early

The problem with the naive method of using the p-value as a stopping criterion is that the statistical test that gives you a p-value assumes that you designed the experiment with a sample and effect size in mind. **If you continuously monitor the development of a test and the resulting p-value, you are very likely to see an effect, even if there is none.**

Another common error is to stop an experiment too early, before an effect becomes visible.

### Example: The Price Filter Experiment

They tested changing the maximum value of the price filter on the search page from $300 to $1000.

The p-value curve hit the commonly used significant value of 0.05 after 7 days, at which point the effect size was 4%. If they had stopped there, they would have concluded that the treatment had a strong and significant effect on the likelihood of booking.

**But they kept the experiment running and found that actually, the experiment ended up neutral.** The final effect size was practically null, with the p-value indicating that whatever the remaining effect size was, it should be regarded as noise.

### Why This Happens

This pattern of hitting "significance" early and then converging back to a neutral result is actually quite common. There are various reasons:

1. **Users often take a long time to book**, so the early converters have a disproportionately large influence in the beginning of the experiment
2. **Even small sample sizes in online experiments are massive** in the scale of classical statistics in which these methods were developed
3. **Most importantly: you are performing a statistical test every time you compute a p-value** and the more you do it, the more likely you are to find an effect

### Best Practices for Experiment Duration

1. **Determine the minimum effect size that you care about** and compute, based on the sample size (the amount of new samples that come every day) and the certainty you want, how long to run the experiment for, **before you start the experiment.** Setting the time in advance also minimizes the likelihood of finding a result where there is none.

2. **Inspect the development of the relevant metrics over time**, rather than to consider the single result of an effect with a p-value. Look at whether trends have converged.

3. **Use a dynamic p-value threshold** if you need to make automated judgment calls. The threshold should be very low at the beginning (be more skeptical of early results), and as more data comes in, you can increase the threshold as the likelihood of finding a false positive is much lower later in the game.

## Understanding Results in Context

**A second pitfall is failing to understand results in their full context.**

In general, it is good practice to evaluate the success of an experiment based on a single metric of interest. This is to prevent cherry-picking of 'significant' results in the midst of a sea of neutral ones. However, by just looking at a single metric you lose a lot of context that could inform your understanding of the effects of an experiment.

### Example: The Search Page Redesign

They redesigned their search page. A lot of work went into the project, and they all thought it was clearly better; their users agreed in qualitative user studies. Despite this, they wanted to evaluate the new design quantitatively with an experiment.

After waiting for enough time to pass, they ended up with a neutral result. The change in the global metric was tiny and the p-value indicated that it was basically a null effect.

However, they decided to look into the context and to break down the result. **Because they did this, they found that the new design was actually performing fine in most cases, except for Internet Explorer.** They then realized that the new design broke an important click-through action for certain older versions of IE, which obviously had a big negative impact on the overall results. When they fixed this, IE displayed similar results to the other browsers, a boost of more than 2%.

### Breaking Down Results

You can break results down by many factors like browser, country, and user type. However, **doing this in the classic A/B testing framework requires some care.** If you test breakdowns individually as if they were independent, you run a big risk of finding effects where there aren't, just like in the example of continuously monitoring the effect.

It's very common to be looking at a neutral experiment, break it down many ways and to find a single 'significant' effect. Declaring victory for that particular group is likely to be incorrect. The reason for this is that you are performing multiple tests with the assumption that they are all independent, which they are not.

**Ways to deal with this:**
- Decrease the p-value by which you decide the effect is real
- Model the effects on all breakdowns directly with a more advanced method like logistic regression

## Assuming the System Works

**The third and final pitfall is assuming that the system works the way you think or hope it does.**

This should be a concern whether you build your own system to evaluate experiments or use a third party tool. In either case, it's possible that what the system tells you does not reflect reality. This can happen either because it's faulty or because you're not using it correctly.

### Run Dummy Experiments (A/A Tests)

A simple way to evaluate the system is to run an experiment where the treatment is equal to the control. These are called **A/A or dummy experiments**. In a perfect world the system would return a neutral result (most of the time).

They ran many 'experiments' like this and identified a number of issues within their own system as a result. In one case, they ran dummy experiments with varying sizes of control and treatment groups:
- Some were evenly split (50% control and 50% treatment group)
- Others had different splits (e.g., 75% control and 25% treatment group)

In the experiments where the control and treatment groups were the same size, the results looked neutral as expected. But, **for the case where the group sizes are different, there was a massive bias against the treatment group.**

They investigated and uncovered a serious issue with the way they assigned visitors that are not logged into treatment groups. The issue is particular to their system, but the general point is that **verifying that the system works the way you think it does is worthwhile and will probably lead to useful insights.**

### Results Too Good to Be True

Another way of looking at this is the observation that **results too good to be true have a higher likelihood of being false.** When you encounter results like this, it is good practice to be skeptical of them and scrutinize them in whatever way you can think of, before you consider them to be accurate.

### Multiple Comparisons

One thing to keep in mind when you run dummy experiments is that you should expect some results to come out as non-neutral. This is because of the way the p-value works. For example, if you run a dummy experiment and look at its performance broken down by 100 different countries, you should expect, on average, 5 of them to give you a non-neutral result. **Keep this in mind when you're scrutinizing a 3rd party tool!**

## Key Takeaways

1. **Determine experiment duration in advance.** Calculate the sample size you need based on the minimum effect size you care about, sample size per day, and desired certainty. Don't stop early just because p-value hits 0.05.

2. **Inspect metric development over time.** Look at whether trends have converged. If an early result doesn't look stable, keep running.

3. **Use dynamic p-value thresholds** for automated decisions. Be more skeptical of early results.

4. **Break down results by meaningful cohorts** but be careful about multiple comparisons. Adjust p-values or use advanced methods to avoid false positives.

5. **Verify your system works.** Run dummy A/A experiments to test your experimentation system. Don't assume it works correctly.

6. **Be skeptical of results that seem too good to be true.** Investigate before accepting them.

7. **Focus on learning, not just optimizing.** Experiments should be run to make good decisions about how to improve the product, rather than to aggressively optimize for a metric. Optimizing can lead to opportunistic decisions for short-term gains.

---

**Sources:**
- [Experiments at Airbnb](https://medium.com/airbnb-engineering/experiments-at-airbnb-e2db3abf39e7) - Jan Overgoor, Airbnb Engineering Blog, May 27, 2014

