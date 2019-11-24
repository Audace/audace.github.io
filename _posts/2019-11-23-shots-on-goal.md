---
layout: post
title: Shots on goal
comments: true
---

I've found myself using the same analogy a good bit the past few months at work. It's about maximizing the number and quality of shots on goal. We're in the midst of launching a consumer product. As we iterate on the concept and work towards achieving product-market-fit, I find the analogy useful for communicating decision making and prioritization. In general, analogies and decision frameworks are great ways to scale decision making. If everyone is aligned on how to make decisions, you don't need to be involved in making every one.

In engineering staff meetings, sprint planning, etc, we'll come across questions like these:
- How much should we prioritize this category of tech debt?
- How robust should the design and implementation of this feature be?
- What, if any, instrumentation and analytics is required to ship?
- How extensive do we need to regression test before shipping?
- Is it better to ship a lot quickly or be very thorough with fewer bets?
- How important is squashing this bug?

These are very standard questions in an early-stage startup. I like framing them in the analogy of **[shots on goal](https://en.wikipedia.org/wiki/Shot_on_goal_(ice_hockey))**. A shot on goal is a metric used in ice hockey and soccer. It means a shot of the puck or ball that was directed to the goal and either went in, or would have gone in. The metric is a proxy for the **number** and **quality** of attempts on goal. If the shot was wildly out of aim, it was not a shot on goal (_quality_). If no shot was able to be taken, it was not a shot on goal (_quantity_).

**Engineers at early stage startups are responsible for maximizing shots on goal.**<sup>1</sup> This means allowing the org to take as many shots as possible and ensuring that they're high quality, or have a chance of going in.

As an engineer, you may not always be deciding what shots to take and how exactly to aim. But, you can ensure that the shots are taken quickly, are high quality, and provide information back to product on their quality. 

Applied towards some of the questions above, you begin to see a few rules of thumb appear:
- Build a feature with the **minimum level of acceptable, engineering effort**

    Overengineering is the worst at early stage startups. Chances are you may scrap the feature altogether. Moreover, should the feature or product take off, you'll likely need to re-architect it for another order
    of magnitude anyway.

- Ensure you spend time to **add analytics**

    There's an important nuance to consider with last two words of the phrase - "on goal". Humans are great at learning and iterating - honing in on a target. In order to make more shots be ones "on goal," you need to know whether each shot was accurate and if not, what needs to be corrected for your next shot to be on goal.
    This is where analytics are important.

- Use **managed services**

    If you find a very compelling argument to build or host a service yourself, please tell me. I find this is rarely the correct answer at early stage startups.

- Make sure you **run [smoke tests](https://en.wikipedia.org/wiki/Smoke_testing_(software))** thoroughly

    If your organization has put in the time to prioritize, define, design, and market a new feature or product,the absolute worst thing to happen is to botch it with critical errors. This results in wasted time and money. It often can affect existing experiments, meaning it'll be hard to know if previous shots were "on goal." Spend time to run the critical tests. This does not need to be automated.

- Align cross-functional team members in **small, cohesive units**

    Small teams move quicker. Get the minimum number of people together. Let them work their magic. You'll definitely get more shots. A higher percentage of them will likely be on goal.

- Prioritize tech debt **only insofar as maximizing quantity and quality of features** you can ship _soon_

    Most tech debt will be irrelevant within a few months. You'll need to tear down the service. The feature will be replaced or removed. Only prioritize tech debt insofar as maximizing shots on goal. If tech debt is preventing you from shipping much more frequently, prioritize it. If tech debt is affecting the quality of your shots, prioritize it.


Obviously, within the lense of a goal being finding product market fit, a feature may not be "on goal" because it wasn't solving an important painpoint. Or fewer shots may be taken because there's a bottleneck before the work hits the tech team. So while I do think that it's important for engineers to provide feedback and input into features and bottlenecks within the org, it's also important for us to prioritize the _shots on goal_ once we have the ball. _Ship high quality features quickly._

[1] Once they've been passed the ball