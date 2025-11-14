# The Limits of Being Data-Driven

**"If we have data, let's look at data. If all we have are opinions, let's go with mine."** —Jim Barksdale

We strive to be data-driven in our decision making. And barring that, data-informed, overlaying our intuition and thoughts on top of the data. We certainly don't want to be ignorant, and just make decisions with our gut. **And yet sometimes that is exactly what happens — and some argue, better than being data-driven.**

There is a great paradox at the heart of using data to make product decisions. While data is meant to be objective and scientific, in practice, it's hardly the case. That's because being data-driven has limitations.

## The Problem

We are endlessly surrounded by data but also lack the ability to make sense of it all. It's enormously frustrating but we commonly encounter discussions with statements like the following:

* "Oh the metrics went down? That's just seasonality. Next quarter will be better"
* "Yes, the metrics are up! That's because of this amazing new thing we just shipped"
* "Yes, the A/B test showed this metric went down but this other went up, so it's actually okay"
* "We have to wait on the A/B test to see how the feature is doing, the data is still collecting"
* "I signed up for a 5% increase last quarter on this key metric, and we hit that goal. Why didn't revenue go up? No idea"
* "People love this feature, just look at the data, we just need to onboard them better!"
* "Our new product feature is totally working, but the current metrics don't reflect it since there's a time lag. Wait until next month"
* "The clickthrough rate on this email was 0.15% and the other was 0.14%. That's why..."
* Etc etc etc

Many of you are now smiling because you've been there! Both on the receiving end, as well as having these kinds of words come out of your mouth :) I know I certainly have.

**Why is it that we have so much data about how people use our products, and we are able to speculate as to what might make them stickier, or more valuable — yet truth-seeking is so difficult?** We get all the aforementioned excuses (and more) because of the "fog of war" as we pick the product. This is doubly critical to figure out as many of our jobs now regularly involve reviewing data, then making decisions. This happens while reviewing dashboards and graphs (at product meetings, reviewing decks, board meetings, etc). Or writing about metrics you're plan to increase as part of a quarterly review. **We are in this fog constantly.**

## The Root Causes

In our quest to be data-driven, we hit many core problems based on how we collect/analyze/decision the data. Here are some of the variations:

### 1. Measuring yesterday when you should be thinking about tomorrow

Data comes from the market you have today, not who you want to have. Products often resonate with a small and loyal audience, but they are often niche, early adopter types. If you make decisions using data from this audience, you may not be able to make the right decisions that get you to a broader market. **Your initial nerdy audience might ask for nerdy/configurable features, or expert features, whereas a broader market wants "easy to use." Your data often doesn't make this argument, and instead you end up chasing a local maximum.**

### 2. Analysis paralysis

The cost of acquiring the data and its analysis can become cost prohibitive. Of course you'd like to have data for every decision. But if you need smart data analysts to pull the data, analyze it, check for corner cases, segment and analyze it, and then call a meeting to discuss (then analyze more, then discuss again), then it'll just take too long. **So it's often better to just analyze the hell out of big things and otherwise ignore the small stuff, even though a truly data-driven team would bristle at this approach.**

### 3. Intuition is fast, A/B tests are slow

Related to the last point, sometimes when you become an expert about the customer, and have great intuition, you just know how to do the right thing. And not just the right thing that can move the needle in the short-term, but also the thing that will create better, long-term value. **You can make a bunch of these decisions quickly, and just ship the product, and not try to A/B test every single one. Sometimes a startup's market is moving so fast that this is actually the right approach.**

### 4. The tyranny of the majority

When you deal with millions of datapoints of usage, you necessarily have to aggregate people together into segments. You look at averages, and compare segments. Yet sometimes these groupings are wrong — what about the VIPs? What about the high value users? If you make decisions that appeal to a broad audience, you might attract low-value international users at the expense of high-value US users — **is more always better?** It takes a while to unentangle which segments you actually care about, particularly if they are the minority of your users.

### 5. A/B tests are good at measuring big things quickly, but not other things

The biggest tool that a data-driven team can use is to use A/B tests. Yet to reach statistical significance quickly, and to iterate on a regular basis (weeks not months), you end up comparing big metrics movements that happen quickly. Signup rate is easy to measure, as is clickthrough rate. **But what about 90 day retention rate for the minority of your users that are the most high-value? That's hard. And so often people just ignore them.**

### 6. There's a lot of noise

Factors like seasonality adds a lot of noise. So do big ad campaigns, or when competitors launch new products, or even if the month you're in has an extra weekend versus another. It's often hard to compare metrics cleanly, so unless there's a big effect, you often have to just grit your teeth and make a guesstimate.

### 7. Historical data may not predict future trends

This is particularly true with emerging technologies. If you take a product idea, and add AI to it, will that be better or worse? Will that increase conversion or retention or put other key metrics into decline? What if you take an idea and add a web3-first design? **Sometimes, technology is just discontinuous and it's impossible to know what will happen next. Sometimes you just have to go for it.** I live with this problem every day in my venture capital job, where you'd like to simplify investing as a "you should always invest when a product has X attribute." But the problem is, the successes are so few (a few dozen a year at most, out of tens of thousands) that you can't really build a high-conviction predictive model.

### 8. Correlation and causation

There's a common path of analysis where a product team tries to figure out how their most engaged users became that in the first place. They quickly find that they do some setup step more often than others — like setting their profile photo or inviting a friend or something. The effect looks strong, and then an A/B test is run forcing everyone to take this step. **The result is… nothing. It turns out high-intent users do X and then become high-intent. It's correlation not causation. Shrug. This appears all the time, in many places, and just wastes everyone's time.**

### 9. Some things are important, but hard to measure

How do you measure the effect of a new product feature on long-term brand? You probably can't. What about how psyched your employees are about a new feature set? Or what investors think? Or maybe you have an n=1 super strategic and important partner you want to impress with some killer new tech. How does that show in an A/B test? **Some of these factors are very important in the success of a new product, but it's hard to get them to show up properly in a graph. Sometimes you just have to make the right call, if these things are important to you.**

I could come up with dozens more of these. **The ultimate point I want to make is that there are a lot of gotchas, and as the webcomics mention, a lot of these data-driven problems will crop up, there are too many dashboards, and too many conflicting opinions. And eventually the "highest paid person" (the HIPPO) just makes the decision, which is often where we started.**

For the more data-driven among you, this might seem horrible. But let me also make the argument that this is great, and actually works!

## Competing Against Tech's Dominant Culture

In the past two decades, because of the success of the Google/Meta product management cultures spreading into many new companies, we have now implemented OKRs across the industry. As a result, we have tens of thousands of product managers signing up for +5% increases in their metrics and aiming their hundreds of thousands of engineers at this problem. **This dominant culture is one of data, of optimization, of taking small concrete steps to move metrics that are big and easy to understand.** And you could argue that the success of many of the biggest tech products — the ones that don't seem to evolve much at their core, but just inch along — are a success based on this strategy.

**What do you do if you are their competitor? For example if you are a startup competing with one of the FAANG companies?**

The reality is, **you can't race their race.** If you are data-driven in the same way they are, have the same dominant PM culture, and make decisions as slow as them, you will lose. They have more resources, can move the ball inches forward each time, and it's hard to win as a result.

**Instead, you may have to do the opposite to compete:**

* **mostly intuition rather than waiting for data**
* **super fast decision-making rather than incremental decisions**
* **big moves rather than small ones**

Of course, I will always advocate to optimize the things worth optimizing for — like signup flows and key notifications. **But a startup's core product strategy might need something more drastic, and intuitive.**

## Data-Driven vs Data-Informed vs Data-Ignorant

I write all of this with the deep pains and scars of using data in almost every product decision I've been apart of over the past decades. Of course I will always use the data. **Yet in my twenties as a feral young founder, I erred towards relying on data too much — a desire to be data-driven, at all costs. But I found that often took me to local maxima.**

Later on, I learned to be data-informed, still having intuition but overlaying data on top. There's a happy medium here. **But I think there is also an argument — particularly for zero-to-one situations — to just be ignorant of the quantitative data, and instead, just train on intuition. Just make decisions based on your expert qualitative opinion about the market, your customers, and your competition. And only optimize based on data later on, when it's more appropriate.**

**The insight:** If success were just a matter of looking at numbers, we'd all be successful. The data sets themselves can tell different stories. You can't just build for the vocal minority. Sometimes you need to trust your intuition, especially when you're competing against well-resourced incumbents or building something entirely new.

---

**Sources:**
- [Why data-driven product decisions are hard (sometimes impossible)](https://andrewchen.substack.com/p/why-its-so-hard-to-be-data-driven) - Andrew Chen, May 28, 2024
- Jim Barksdale quote

