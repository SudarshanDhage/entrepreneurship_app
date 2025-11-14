# Never Rewrite Code From Scratch

Joel Spolsky's famous warning: rewriting code from scratch is "the single worst strategic mistake that any software company can make." Why old code is valuable, what "messy" code actually contains, and how to fix problems without throwing everything away.

## The Netscape Story

**Netscape 6.0:** Netscape 6.0 finally went into its first public beta. There never was a version 5.0. The last major release, version 4.0, was released almost three years ago. Three years is an *awfully* long time in the Internet world. During this time, Netscape sat by, helplessly, as their market share plummeted.

**The mistake:** They didn't do it on purpose—or did they? Well, yes. They did. They did it by making the **single worst strategic mistake** that any software company can make:

**They decided to rewrite the code from scratch.**

## Historical Examples

**Netscape wasn't alone:** Netscape wasn't the first company to make this mistake.

**Borland:**
- Made the same mistake when they bought Arago and tried to make it into dBase for Windows, a doomed project that took so long that Microsoft Access ate their lunch
- Made it again in rewriting Quattro Pro from scratch and astonishing people with how few features it had

**Microsoft:**
- Almost made the same mistake, trying to rewrite Word for Windows from scratch in a doomed project called Pyramid which was shut down, thrown away, and swept under the rug
- Lucky for Microsoft, they had never stopped working on the old code base, so they had something to ship, making it merely a financial disaster, not a strategic one

## Why Programmers Want to Rewrite

**We're architects:** We're programmers. Programmers are, in their hearts, architects, and the first thing they want to do when they get to a site is to bulldoze the place flat and build something grand. We're not excited by incremental renovation: tinkering, improving, planting flower beds.

**The subtle reason:** There's a subtle reason that programmers always want to throw away the code and start over. The reason is that they think the old code is a mess. And here is the interesting observation: *they are probably wrong.*

**The fundamental law:** The reason that they think the old code is a mess is because of a cardinal, fundamental law of programming:

> **It's harder to read code than to write it.**

**Why code reuse is hard:** This is why code reuse is so hard. This is why everybody on your team has a different function they like to use for splitting strings into arrays of strings. They write their own function because it's easier and more fun than figuring out how the old function works.

**The universal complaint:** As a corollary of this axiom, you can ask almost any programmer today about the code they are working on. "It's a big hairy mess," they will tell you. "I'd like nothing better than to throw it out and start over."

## Why Code Seems Messy

**The two-page function:** "Well," they say, "look at this function. It is two pages long! None of this stuff belongs in there! I don't know what half of these API calls are for."

**Those "hairs" are bug fixes:** Back to that two page function. Yes, I know, it's just a simple function to display a window, but it has grown little hairs and stuff on it and nobody knows why. Well, I'll tell you why: **those are bug fixes.**

- One of them fixes that bug that Nancy had when she tried to install the thing on a computer that didn't have Internet Explorer
- Another one fixes that bug that occurs in low memory conditions
- Another one fixes that bug that occurred when the file is on a floppy disk and the user yanks out the disk in the middle
- That LoadLibrary call is ugly but it makes the code work on old versions of Windows 95

**The hidden value:** Each of these bugs took weeks of real-world usage before they were found. The programmer might have spent a couple of days reproducing the bug in the lab and fixing it. If it's like a lot of bugs, the fix might be one line of code, or it might even be a couple of characters, but a lot of work and time went into those two characters.

## The Cost of Rewriting

**You throw away knowledge:** When you throw away code and start from scratch, you are throwing away all that knowledge. All those collected bug fixes. Years of programming work.

**You throw away market leadership:** You are throwing away your market leadership. You are giving a gift of two or three years to your competitors, and believe me, that is a *long* time in software years.

**You can't react to the market:** You are putting yourself in an extremely dangerous position where you will be shipping an old version of the code for several years, completely unable to make any strategic changes or react to new features that the market demands, because you don't have shippable code. You might as well just close for business for the duration.

**You waste money:** You are wasting an outlandish amount of money writing code that already exists.

## Why Old Code is Valuable

**Old code has been used:** The idea that new code is better than old is patently absurd. Old code has been *used*. It has been *tested*. *Lots* of bugs have been found, and they've been *fixed*. There's nothing wrong with it. It doesn't acquire bugs just by sitting around on your hard drive.

**Software doesn't rust:** Au contraire, baby! Is software supposed to be like an old Dodge Dart, that rusts just sitting in the garage? Is software like a teddy bear that's kind of gross if it's not made out of *all new material*?

**The Borland fallacy:** Before Borland's new spreadsheet for Windows shipped, Philippe Kahn, the colorful founder of Borland, was quoted a lot in the press bragging about how Quattro Pro would be much better than Microsoft Excel, because it was written from scratch. All new source code! As if source code *rusted*.

**Netscape worked:** Is there an alternative? The consensus seems to be that the old Netscape code base was *really* bad. Well, it might have been bad, but, you know what? It worked pretty darn well on an awful lot of real world computer systems.

## What's Actually Wrong With "Messy" Code

When programmers say that their code is a holy mess (as they always do), there are three kinds of things that are wrong with it:

### 1. Architectural Problems

**The problem:** The code is not factored correctly. The networking code is popping up its own dialog boxes from the middle of nowhere; this should have been handled in the UI code.

**The solution:** These problems can be solved, one at a time, by carefully moving code, refactoring, changing interfaces. They can be done by one programmer working carefully and checking in his changes all at once, so that nobody else is disrupted.

**Even major changes can be done incrementally:** Even fairly major architectural changes can be done without *throwing away the code*. On the Juno project we spent several months rearchitecting at one point: just moving things around, cleaning them up, creating base classes that made sense, and creating sharp interfaces between the modules. But we did it carefully, with our existing code base, and we didn't introduce new bugs or throw away working code.

### 2. Inefficiency

**The problem:** The code is inefficient. The rendering code in Netscape was rumored to be slow.

**The solution:** But this only affects a small part of the project, which you can optimize or even rewrite. You don't have to rewrite the whole thing. **When optimizing for speed, 1% of the work gets you 99% of the bang.**

### 3. Ugliness

**The problem:** The code may be doggone ugly. One project I worked on actually had a data type called a FuckedString. Another project had started out using the convention of starting member variables with an underscore, but later switched to the more standard "m_". So half the functions started with "_" and half with "m_", which looked ugly.

**The solution:** Frankly, this is the kind of thing you solve in five minutes with a macro in Emacs, not by starting from scratch.

## The Rebuild Fallacy

**No reason to do better:** It's important to remember that when you start from scratch there is **absolutely no reason** to believe that you are going to do a better job than you did the first time. First of all, you probably don't even have the same programming team that worked on version one, so you don't actually have "more experience". You're just going to make most of the old mistakes again, and introduce some new problems that weren't in the original version.

## When "Build One to Throw Away" Applies

**The dangerous mantra:** The old mantra *build one to throw away* is dangerous when applied to large scale commercial applications.

**When it's fine:**
- If you are writing code experimentally, you may want to rip up the function you wrote last week when you think of a better algorithm. That's fine.
- You may want to refactor a class to make it easier to use. That's fine, too.

**When it's folly:** But throwing away the whole program is a dangerous folly, and if Netscape actually had some adult supervision with software industry experience, they might not have shot themselves in the foot so badly.

## Key Takeaways

1. **Rewriting from scratch is the worst strategic mistake** - It throws away years of bug fixes and knowledge.

2. **Old code is valuable** - It's been used, tested, and had bugs fixed. Software doesn't rust.

3. **"Messy" code contains bug fixes** - Those "hairs" on functions are often fixes for real-world edge cases that took weeks to discover and fix.

4. **It's harder to read code than write it** - This fundamental law explains why code always seems messy.

5. **Architectural problems can be fixed incrementally** - You don't need to rewrite. Refactor carefully, move code, change interfaces.

6. **Inefficiency is localized** - Optimize the slow parts. 1% of the work gets you 99% of the speed improvement.

7. **Ugliness is trivial** - Use macros, find/replace, refactoring tools. Don't rewrite for cosmetic reasons.

8. **You won't do better the second time** - You'll make the same mistakes again, plus new ones.

9. **You throw away market leadership** - You give competitors 2-3 years (a long time in software).

10. **You can't react to the market** - You're stuck shipping old code while competitors innovate.

11. **"Build one to throw away" is dangerous** - Fine for experimental code, folly for commercial applications.

12. **Refactor, don't rewrite** - Incremental improvements preserve knowledge while fixing problems.

---

**Source:** [Things You Should Never Do, Part I](https://www.joelonsoftware.com/2000/04/06/things-you-should-never-do-part-i/), Joel on Software by Joel Spolsky (April 6, 2000). Joel Spolsky co-founded Fog Creek Software (FogBugz, Trello, Glitch) and Stack Overflow, serving as CEO from 2010-2019.

