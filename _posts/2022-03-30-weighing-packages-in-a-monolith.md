---
layout: post
title: "Weighing package management in a monolithic environment"
category: articles
tags: [code, package]
---

## **Potential for repo overload**

> How do we establish a strong process in practice? How easy is it from an on-boarding perspective as a new(er) engineer having to know/consume all these repos? How well will engineering adapt to so many changes?

Discoverability and on-boarding are huge concerns! I think we should be weighing most of our decisions with learnability and cognitive overhead in mind. We should be looking for ways to cut down on the friction of changes — especially while in a time of architectural uncertainty.

When looking at separate repos and packaging, I agree it can *add* friction. Every change suddenly requires this seemingly huge effort of actually writing the code, maintaining APIs, defining breaking changes, and keeping mental track of packaged version in conjunction with git branches/forks/milestones. Then, of course, there's documenting and publishing. It's easy to bucket all of this work as overhead and see it negatively.

This friction is especially evident when you consider the monolith approach. Inside `@product/mailchimp` folks can make whatever changes necessary with little-to-no overhead. By nature, the dependency chain is short and very discoverable. This is huge and can be a wonderful time saver.

Sounds good right? Maybe we should reconsider this whole separate repo thing entirely? But not everything within monoliths is awesome. Monoliths can lead to fuzzy boundaries between bits of code. Velocity of new code authorship often increases — the tradeoff is that refactoring and code removal becomes more difficult. Although code is written modularly, there's no guarantee that it will be consumed and applied modularly. CSS in a global scope is a great example of this.

I'm making some large generalizations about monoliths for a point. There are always exceptions to what I just wrote. Overall, we have a very functional monolith setup.

You'll often hear code boundaries being discussed in terms of [separation of concerns](https://en.wikipedia.org/wiki/Separation_of_concerns). Essentially this boils down to: code that has a specific and limited purpose is usually easier to contribute to and use. This has parallels in how we manage git repositories and dependencies. Repositories that have a specific and limited purpose are also easier to contribute to. Each of them could have their own set of tests, tools, and documentation that are especially tuned to the concerns of that repository.

Of course this has an upper bound. If we over-abstract and have too many repositories or packages, overhead goes up. Similarly if we clump everything together, overhead also goes up (just in a different way). So it's all a balancing act that requires some human gut checks.

Assuming you need code in more than one place and change is a constant, I would summarize my thought process like so:

```js
// Please ignore that these are stings. These would be truthy and this JS wouldn't run.*
let changeOverhead = "How much toil is involved in making changes?";
let entropy =
  "Lack of order or predictability; gradual decline into disorder. How crazy will things get if we duplicate code instead of packaging?";
let numConsumers = "How many teams/tools/repos will use this?";

const shouldMakeAsPackage = () => {
  return changeOverhead < entropy * numConsumers;
};
```

To reiterate: *If it will be more work to manage changes in multiple places than managing it as a package, we should probably make it as a package.* As the number of consumers or complexity increases, the overhead can be seen as inversely proportional.

To put it another way, regardless of whether we are duplicating or packaging, we are incurring a cost. It comes down to what cost our team is comfortable approaching.

## **Approaching overhead as a necessary cost to package management**

As I hope I illustrated, overhead is somewhat inevitable when building and maintaining systems. Let's look at onboarding, learnability, and discoverability again.

Something I find these topics have in common is that they are [known known](https://www.pmi.org/learning/library/characterizing-unknown-unknowns-6077) problems — Every team will face them. I wouldn't say they are easy but they can be addressed through coaching, documentation, and independent study. I believe through good processes, communication, and team building we can adequately address the cognitive load contribution requires.

In comparison, Entropy falls more into the [unknown unknown](https://marketbusinessnews.com/financial-glossary/financial-glossary-u/unknown-unknowns/) territory. We know change will happen but have limited control over what it is or when. This puts our team in a reactionary and policing stance which could easily be a losing position. This is an overgeneralization and assumes a relatively complex module.

Concluding, creating additional repos and packages will incur a debt to these topics — it makes all of them harder. The question I'd suggest is whether there's potential for it to be a **net positive**. Will it be easier to teach dependencies/repos than the alternative?
