# Platforms vs Products: The Steve Yegge Rant

Why platforms beat products: Amazon's transformation into a platform company, Google's failure to "get" platforms, and why "a platform-less product will always be replaced by an equivalent platform-ized product."

## The Amazon vs Google Story

**The setup:** I was at Amazon for about six and a half years, and now I've been at Google for that long. One thing that struck me immediately about the two companies—an impression that has been reinforced almost daily—is that Amazon does everything wrong, and Google does everything right.

**The reality:** But there's one thing Amazon does really really well that pretty much makes up for ALL of their political, philosophical and technical screw-ups. **They understand platforms.**

**Google doesn't get platforms:** That one last thing that Google doesn't do well is Platforms. We don't understand platforms. We don't "get" platforms. Some of you do, but you are the minority.

## Jeff Bezos's Big Mandate

**The context:** Jeff Bezos is an infamous micro-manager. He micro-manages every single pixel of Amazon's retail site. But one day—back around 2002—he issued a mandate that was so out there, so huge and eye-bulgingly ponderous, that it made all of his other mandates look like unsolicited peer bonuses.

**The mandate:**

1. All teams will henceforth expose their data and functionality through service interfaces.
2. Teams must communicate with each other through these interfaces.
3. There will be no other form of interprocess communication allowed: no direct linking, no direct reads of another team's data store, no shared-memory model, no back-doors whatsoever. The only communication allowed is via service interface calls over the network.
4. It doesn't matter what technology they use. HTTP, Corba, Pubsub, custom protocols—doesn't matter. Bezos doesn't care.
5. **All service interfaces, without exception, must be designed from the ground up to be externalizable.** That is to say, the team must plan and design to be able to expose the interface to developers in the outside world. No exceptions.
6. Anyone who doesn't do this will be fired.
7. Thank you; have a nice day!

**The enforcement:** Bezos assigned a couple of Chief Bulldogs to oversee the effort, headed up by Rick Dalzell—an ex-Army Ranger, West Point Academy graduate, ex-boxer, ex-Chief Torturer slash CIO at Wal*Mart. Everyone made LOTS of forward progress.

## Amazon's Service-Oriented Architecture Transformation

**The transformation:** Over the next couple of years, Amazon transformed internally into a service-oriented architecture. They learned a tremendous amount while effecting this transformation.

**Key discoveries at scale:**

- **Pager escalation gets way harder** - A ticket might bounce through 20 service calls before the real owner is identified. If each bounce goes through a team with a 15-minute response time, it can be hours before the right team finally finds out.

- **Every peer team becomes a potential DOS attacker** - Nobody can make any real forward progress until very serious quotas and throttling are put in place in every single service.

- **Monitoring and QA are the same thing** - When your service says "oh yes, I'm fine", it may well be the case that the only thing still functioning is the little component that knows how to say "I'm fine, roger roger, over and out". In order to tell whether the service is actually responding, you have to make individual calls. The problem continues recursively until your monitoring is doing comprehensive semantics checking, at which point it's indistinguishable from automated QA.

- **Service discovery is essential** - If you have hundreds of services, and your code MUST communicate with other groups' code via these services, then you won't be able to find any of them without a service-discovery mechanism. And you can't have that without a service registration mechanism, which itself is another service.

- **Debugging gets harder** - Debugging problems with someone else's code gets a LOT harder, and is basically impossible unless there is a universal standard way to run every service in a debuggable sandbox.

**Cultural shift:** Amazon transformed culturally into a company that thinks about everything in a services-first fashion. It is now fundamental to how they approach all designs, including internal designs for stuff that might never see the light of day externally. They don't even do it out of fear of being fired anymore—they do services because they've come to understand that it's the Right Thing.

## Why Platforms Matter

**Platforms enable accessibility:** Bezos realized that he can't always build the right thing. There's actually a formal name for this phenomenon. It's called **Accessibility**, and it's the most important thing in the computing world.

**The. Most. Important. Thing.**

**What accessibility means:** If you're thinking "huh? You mean like, blind and deaf people Accessibility?" then you're not alone. When software—or idea-ware for that matter—fails to be accessible to anyone for any reason, it is the fault of the software or of the messaging of the idea. It is an Accessibility failure.

**Platforms solve accessibility:** Platforms solve accessibility. A platform is accessibility. You can't build one product that's right for everyone. But you can enable third-party developers to build the right product for everyone.

**The accessibility vs security tension:** Accessibility has an evil twin named Security. And boy howdy are the two ever at odds. But Accessibility is actually more important than Security because dialing Accessibility to zero means you have no product at all, whereas dialing Security to zero can still get you a reasonably successful product such as the Playstation Network.

## The Platform-Product Relationship

**Amazon's realizations:**

**1. Infrastructure as a platform:** The infrastructure they'd built for selling and shipping books could be transformed into an excellent repurposable computing platform. So now they have AWS: EC2, EMR, RDS, and a whole passel of other services.

**2. You can't build the right thing for everyone:** Bezos can't always build the right thing. Larry Tesler might have struck some kind of chord when he said his mom couldn't use the goddamn website. It doesn't matter whose mom—nobody's mom can use the goddamn website. But Bezos gets it: he can enable third-party developers to do it, and it would happen automatically.

**The fundamental principle:** A product is useless without a platform, or more precisely and accurately, **a platform-less product will always be replaced by an equivalent platform-ized product.**

## Google's Failure: Google+

**The example:** Google+ is a prime example of our complete failure to understand platforms from the very highest levels of executive leadership down to the very lowest leaf workers. We all don't get it.

**The Golden Rule of Platforms:** **Eat Your Own Dogfood.** The Google+ platform is a pathetic afterthought. We had no API at all at launch, and last I checked, we had one measly API call. One measly API call to get someone's stream.

**The wrong thinking:** Our Google+ team took a look at the aftermarket and said: "Gosh, it looks like we need some games. Let's go contract someone to, um, write some games for us." Do you begin to see how incredibly wrong that thinking is? The problem is that we are trying to predict what people want and deliver it for them.

**You can't do that:** You can't do that. Not really. Not reliably. There have been precious few people in the world who have been able to do it reliably. Steve Jobs was one of them. We don't have a Steve Jobs here.

**Facebook's success:** Facebook is successful because they built an entire constellation of products by allowing other people to do the work. So Facebook is different for everyone. Some people spend all their time on Mafia Wars. Some spend all their time on Farmville. There are hundreds or maybe thousands of different high-quality time sinks available, so there's something there for everyone.

**The platform lesson:** The Facebook App could have been anywhere near as successful without the Facebook Platform. The killer app for the Facebook Platform is Facebook itself—the stock service with walls and friends. But it is a very serious mistake to conclude that the Facebook App could have been anywhere near as successful without the Facebook Platform.

## Who Gets Platforms?

**Microsoft gets it:** Microsoft has known about the Dogfood rule for at least twenty years. It's been part of their culture for a whole generation now. They have thousands, and thousands, and THOUSANDS of API calls. They have a HUGE platform. Too big in fact, because they can't design for squat, but at least they're doing it.

**Amazon gets it:** Amazon's AWS is incredible. Just go look at it. Click around. It's embarrassing that we don't have any of that stuff.

**Apple gets it:** They've made some fundamentally non-open choices, particularly around their mobile platform. But they understand accessibility and they understand the power of third-party development and they eat their dogfood. Their APIs are a hell of a lot cleaner than Microsoft's.

**Facebook gets it:** That's what really worries me. That's what got me off my lazy butt to write this thing.

**Google doesn't get it:** Head over to developers.google.com and browse a little. Pretty big difference, eh? It's like what your fifth-grade nephew might mock up if he were doing an assignment to demonstrate what a big powerful platform company might be building if all they had, resource-wise, was one fifth grader.

## The Cultural Problem at Google

**It's a cultural thing:** What we have going on internally is basically a war, with the underdog minority Platformers fighting a more or less losing battle against the Mighty Funded Confident Producters.

**The underdog teams:** Any teams that have successfully internalized the notion that they should be externally programmable platforms from the ground up are underdogs—Maps and Docs come to mind, and I know GMail is making overtures in that direction. But it's hard for them to get funding for it because it's not part of our culture.

**The funding problem:** Maestro's funding is a feeble thing compared to the gargantuan Microsoft Office programming platform: it's a fluffy rabbit versus a T-Rex. The Docs team knows they'll never be competitive with Office until they can match its scripting facilities, but they're not getting any resource love.

**Wave was a great platform:** Ironically enough, Wave was a great platform, may they rest in peace. But making something a platform is not going to make you an instant success. A platform needs a killer app.

## The Arrogance Problem

**We're not arrogant, except when we are:** You know how people are always saying Google is arrogant? We're not arrogant, by and large. We're, like, 99% Arrogance-Free. But when we take the stance that we know how to design the perfect product for everyone, and believe you me, I hear that a lot, then we're being fools.

**There IS no perfect product for everyone:** You can attribute it to arrogance, or naivete, or whatever—it doesn't matter in the end, because it's foolishness. There IS no perfect product for everyone.

**The Chrome example:** We wind up with a browser that doesn't let you set the default font size. Talk about an affront to Accessibility. The Chrome team is flat-out arrogant here: they want to build a zero-configuration product, and they're quite brazen about it, and Fuck You if you're blind or deaf or whatever. Hit Ctrl-+ on every single page visit for the rest of your life.

## Why We're a Product Company

**We built a successful product:** We're a Product Company through and through. We built a successful product with broad appeal—our search, that is—and that wild success has biased us.

**How others transitioned:**

- **Amazon** - Was a product company too, so it took an out-of-band force to make Bezos understand the need for a platform. That force was their evaporating margins; he was cornered and had to think of a way out. But all he had was a bunch of engineers and all these computers... if only they could be monetized somehow... you can see how he arrived at AWS.

- **Microsoft** - Started out as a platform, so they've just had lots of practice at it.

- **Facebook** - Started off as a Product and rode that success pretty far. So I'm not sure exactly how they made the transition to a platform. Maybe they just looked at us and asked: "How can we beat Google? What are they missing?"

## The Solution

**Dramatic cultural change needed:** The problem we face is pretty huge, because it will take a dramatic cultural change in order for us to start catching up. We don't do internal service-oriented platforms, and we just as equally don't do external ones. This means that the "not getting it" is endemic across the company: the PMs don't get it, the engineers don't get it, the product teams don't get it, nobody gets it.

**We can't bolt it on later:** The Golden Rule of Platforms, "Eat Your Own Dogfood", can be rephrased as **"Start with a Platform, and Then Use it for Everything."** You can't just bolt it on later. Certainly not easily at any rate—ask anyone who worked on platformizing MS Office. Or anyone who worked on platformizing Amazon. If you delay it, it'll be ten times as much work as just doing it correctly up front.

**No cheating:** You can't cheat. You can't have secret back doors for internal apps to get special priority access, not for ANY reason. You need to solve the hard problems up front.

**It's not too late, but...** I'm not saying it's too late for us, but the longer we wait, the closer we get to being Too Late.

## Key Takeaways

1. **Platforms beat products** - A platform-less product will always be replaced by an equivalent platform-ized product.

2. **Platforms solve accessibility** - You can't build one product that's right for everyone. Platforms enable third-party developers to build the right product for everyone.

3. **Eat your own dogfood** - The Golden Rule of Platforms: design for external use from the start, even for internal services.

4. **Start with a platform, use it for everything** - You can't bolt it on later. It's ten times as much work.

5. **No cheating** - No secret back doors for internal apps. Solve the hard problems up front.

6. **Bezos's mandate worked** - Force all teams to expose interfaces. Make them externalizable from day one. It transformed Amazon culturally.

7. **SOA lessons at scale** - Service discovery, monitoring, debugging, pager escalation all get harder. Quotas and throttling are essential.

8. **You can't predict what people want** - You can't reliably build the perfect product for everyone. Only a few people like Steve Jobs could do it. Enable others instead.

9. **Platforms need killer apps** - A platform won't make you an instant success. It needs a killer app (like Facebook itself for the Facebook Platform).

10. **It's a cultural problem** - Not understanding platforms is endemic. PMs don't get it, engineers don't get it, product teams don't get it.

11. **Accessibility is more important than security** - Dialing accessibility to zero means you have no product at all.

12. **The infrastructure realization** - Amazon realized their book-selling infrastructure could be repurposed as a computing platform (AWS).

13. **Microsoft, Amazon, Apple, Facebook get it** - Google doesn't, and it's costing them.

14. **We're a product company** - Our success with search biased us. We need to become a platform company.

---

**Source:** [Stevey's Google Platforms Rant](https://gist.github.com/chitchcock/1281611), Steve Yegge (October 11, 2011). Originally written as an internal Google+ post that was accidentally made public. Steve Yegge worked at Amazon for 6.5 years and Google for 6.5 years, providing unique insights into both companies' approaches to platforms.

