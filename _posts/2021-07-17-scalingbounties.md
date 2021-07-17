---
title: "Sliding Bounties and Why You Should Use Them"
date: 2021-07-17
---

If you've been doing bug bounty for any time, either as a hunter or a program, you've doubtless heard complaints about CVSS scoring. The typical scenario will look something like this - a hacker will file a report (likely with a laughably inflated CVSS score), set the severity that they think the report is, get their expectations set on receiving $X, the triage service will validate the report, and assign a score using a [CVSS Caculator](https://www.first.org/cvss/calculator/3.1#CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:N/I:N/A:N) and mark the report as `Triaged` (barring any back and forth around reproduction steps). 

Now almost certainly the CVSS score will be lower than what the hacker had initially set, meaning that the hacker will receive a smaller than expected bounty, begetting disappointment. As both a bug hunter and a program manager, I've experienced this on multiple occasions. I've slapped a `Low` severity on bugs submitted to my program as a `High` and had to deal with days of arguing back and forth, and I've had my own `High`s turn into `Low`s. Either way, a less than desirable experience is had for all parties involved. This got me thinking about what the actual problem might be. Is CVSS a relic of the past that should be eliminated from the bug bounty industry? Should programs and triagers give hackers the benefit of the doubt? Should hackers lowball the severity of their reports to reduce disappointment? I think the problem (and solution) are deeper than that. So let's start by digging into what I like about CVSS.


### The Good

- It's fast: Rather than spend hours discussing with your security team, punching in numbers takes about 30 seconds and it spits out a number.
- It's objective: CVSS ensures that the same bug submitted at two different times will always be given the same score, regardless of who's assigning the score. 
- It's popular: While I don't necessarily agree that just because everyone does something, it _should_ be done that way; there IS something to be said about having a system that's universally accepted by the majority of organizations

### But...

When thinking about the above, it's hard to argue against using CVSS. But then why did I find myself getting upset at it all the time? To answer this I need to examine the CVSS metric that causes me the most grief: `Privileges Required`.

For those not familiar, the `Privileges Required` (or `PR`) metric has 3 values: `None`, `Low`, and `High`. According to the CVSS documentation, a score of `None` is used for when the attacker is completely unauthenticated. Think of this as when you've mistakenly got a sensitive application exposed on a port you weren't aware of. `Low` is for when the user has been authenticated to the system, but isn't given any heavy permissions. And `High` is for when the attacker requires extensive permissions to the application. Now that's all find and dandy...until you think about CVSS in the context of a _SaaS application_. 

Let's imagine you have an application where a user can perform attacks on any other user. Obviously, if you've been provisioned an account on the application, then the attack is obviously less severe than if the attacker could be anyone on the interenet, right? Of course. So the `PR` would be set to `Low`, since you need to be authenticated into the application. I have no disagreement there. _However_ within the context of a SaaS application, it's quite common for users to provision themselves an account for free. Meaning that there is effecitively no implicit trust given to an authenicated user. So while the attacker might be authenticated, no one has "granted" them this authenticated access. As such, a bug that can leak mass amounts of data which everyone would agree _should_ be a [7.5 High](https://www.first.org/cvss/calculator/3.1#CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:N/A:N) gets treated as [6.5 Medium](https://www.first.org/cvss/calculator/3.1#CVSS:3.1/AV:N/AC:L/PR:L/UI:N/S:U/C:H/I:N/A:N)

### The Problem

So is CVSS flawed? Well...no. CVSS is doing exactly what it's supposed to do. It's providing a standardized score to a bug, which can be applied regardless of the program/bug. It is slightly unfortunate that requiring a self-signup drops the score by 1 point, but all things considered that isn't a lot.

So what's the big deal then, Douglas? Are you really upset that your bug is scored as a `Medium` instead of a `High`? That's what I thought initially, but I dug deeper and found that the reason I kept getting upset wasn't because of the severity, but because the _bounty_. I'll explain. 

Most bug bounty programs (especially newer ones) will have a bounty structure that looks like this:

| Severity | Bounty |
| --- | --- |
| Low | $100 |
| Medium | $500 |
| High | $2,000 |
| Critical | $5,000 |

So when a bug drops a _tenth of a CVSS point_ from `7.0 High` to `6.9 Medium`, it isn't just a difference in severity. It's a _$1,500_ difference in severity. So certainly when you've got a bug that drops from a `High` to a `Medium` because it requires the attacker to spend 15 seconds creating a free-trial on that SaaS application, it's going to sting. And the larger the delta between bounties the stingier the sting, and the more disagreements around CVSS scoring between reporter and triager will be had. 

### The Solution

So when I realized that my frustration wasn't coming from CVSS itself, but rather the large difference in bounties between severities, I started to think back to some of the positive experience I've had on programs, and which programs seemed to mitigate this frustration. [Shopify's Bug Bounty Program](https://hackerone.com/shopify?type=team) came to mind. The way they handle CVSS is with this nifty [calculator](https://shopify.github.io/appsec/cvss_calculator/) where you punch in the CVSS metrics and it tells you what the bounty will be. Yes! This is great for 2 reasons. First, it sets your bounty expectations ahead of time, but secondly (and more importantly), it decides the bounty based on the SCORE and not the SEVERITY. Meaning that rightfully, a `6.9 Medium` will pay significantly more than a `4.0 Medium`. In otherworse, they have a sliding _bounty scale_ rather than a rigid _bounty table_.

Imagine the following bounty structure instead:

| Severity | Bounty |
| --- | --- |
| Low | $100-$400 |
| Medium | $500-$1,900 |
| High | $2,000-$4,900 |
| Critical | $5,000-$10,000 |

In the above exmaple, if you submitted a `7.0 High` and it got downgraded to `6.9 Medium`, your bounty may only drop by `$100` rather than the `$1,500` from before. Furthremore, if a bug got increased from a `8.9 High` to a `9.0 Critical`, the program wouldn't be forced to pay an additional `$3,000` due to such a minor change. Crisis averted and all sides happy!

### Conclusion

So if you're running a bug bounty program, or thinking about running one, please consider implementing a sliding bounty scale over a rigid bounty table. And if you're a bug bounty platform who onboards new programs on the regular, perhaps encourage them to consider this method as well :)

Oh, and while CVSS may have some rough spots, from the program perspective, it's REALLY nice to be able to come to a severity decision quickly, which means the researcher can get paid quickly. A happy program makes happy hackers (and vice versa)!
