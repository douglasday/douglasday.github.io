---
title: "Map your hacking sessions- then execute"
date: 2021-10-09
---

Bug Bounty Hunting is an ever-changing ecosystem - what works in one season may not work in another. As such, and as with any discipline, being able to evaluate your self and adjust your course when thing stops working is imperative.

As a succesful bug bounty hunter, I am in a _lot_ of private programs. Additionally, the [Hackerone Directory](hackerone.com/directory) is always getting larger. While this has the benefit of making the surface area for bug hunting _unimaginably large_, it also fosters my personal achilles heel: Decision Paralysis.

Not too long ago, I sat down for my weekly Wednesday night hacking session after taking a week or two off to celebrate a personal milestone. But when I logged in to HackerOne, I froze. I had a countless amount of programs to hack on but didn't know which to actually dive into. Should I start going deep into a program that I haven't touched before? Should I look at some recent invites and try to get some quick low-hanging fruit? Should I go back to one of my trusty old programs that I know really well? I sat there for a good 20-30 minutes of my alloted 2 hour hacking window unable to proceed. After looking at the clock and freaking out for a minute that I wasted so much time, I decided to just open up my list of private programs and picked a newer one and started hacking without any real direction. Unsurprisingly, I didn't find anything in the first 20 minutes, so I got frustrated and moved on to another program. Again, I didn't find anything and after not too long, I pivoted to another program. Eventually, my 2 hour hacking period was up, I was more Bug-less Day than Douglas Day, and I felt like I wasted an entire 2 hours that could have been spent doing something more enjoyable.

I'm sure I'm not the only one who's experienced something similar. You don't know what to hack on, so you just flit between various apps failing to find anything, getting discouraged, and moving on without ever getting deep enough into an application to gain the level of understanding needed to find bugs. 

I knew I needed to implement _some_ amount of change to my approach, otherwise I'd hit that burnout that we all fear. Below is what I have done so far:

### My Solution

The crux of the problem above wasn't that I wasn't finding bugs - it's that I wasn't feeling like I was using my time productively. Everyone has days where they don't find any bugs. That's okay. Those days where don't find any bugs, you should at least have gained knowledge about your target, getting you closer to bugs in the future. But when you didn't find any bugs AND you aren't any closer to finding bugs - that's demoralizing. So how could I get to a point where I didn't feel bad about not finding any bugs?

A read a quote by modern stoic philosopher William B Irvine:

> Remember that among the things over which we have complete control are the goals we set for ourselves. I think that when a stoic concerns himself with things over which he has some but not complete control, such as winning a tennis match, he will be very careful about the goals he sets for himself. In particular, he will be careful to set internal rather than external goals. Thus, his goal in playing tennis will not be to win a match (something external, over which he has only partial control) but to play to the best of his ability in the match (something internal, over which he has complete control). By choosing this goal, he will spare himself frustration and disappointment should he lose the match: since it was not his goal to win the match, he will not have failed to attain his goal, as long as he played his best. His tranquility will not be disrupted.

So when it came to bug hunting, I was setting up an _external_ goal (finding X number of bugs, or making X number of dollars), rather than an _internal_ goal. And since finding bugs is never guaranteed, I was setting myself up for disappointment, by pegging my attitude on something that I didn't have complete control over. So if to fix this I needed to set an _internal_ goal, what should that internal goal be?

To answer that, I initially thought it should be something like "Make sure you always try your hardest" or "Never quit when the bugs are hard to find", but I didn't really like having something so ephemeral and unquantifiable. Rather, I decided to start every defined hacking session with an outlined & scoped plan, and then when it came to hacking all I had to do was execute the plan. So here's an example.

Let's say it's Wednesday night and I am going to hack from 16:00-19:00 before dinnertime. That's three hours of hacking and I want to make the most out of it. As I mentioned earlier, jumping from programA to programB to programC in 20 minute chunks is NOT an effective use of that time. So about 10-20 minutes _before_ 16:00, I'll make a plan that looks like this:


```
Hacking Time: 3 Hours

16:00-16:45 - Hack on Shopify, focusing on giftcard manipulation
16:45-17:30 - Continue on Shopify, but switch to looking at the authentication model.
17:30-18:30 - Start looking at PayPal, focusing on Venmo transaction comments.
18:30-19:00 - Write any reports for bugs you've found. If no bugs, keep hacking on PayPal
```

At the end of my hacking session I'll be in one of 4 states:

1. I executed the plan and found bugs - Good!
2. I executed the plan and didn't find bugs - Good! 
3. I didn't execute the plan and found bugs - Good!
4. I didn't execute the plan and didn't find bugs - Bad!

Since my internal goal was NOT to find bugs (something I have only partial control over), but to execute the plan (something I have complete control over), then whether I found bugs or not, I still had a productive three hours. And because I spend a solid amount of time getting deeper into the programs I was hacking on, I'm more prepared and knowledgable about the applications, increasing my odds of finding bugs the _next_ time I hack on them with a plan.

### In Conclusion

Ultimately, there's no wrong or right way to do hacking. Some folks have great success just picking up a target on a whim! But if you're like me and struggle with decision paralysis and struggle getting deep enough into an application to find bugs, then try mapping out your hacking session ahead of time and only focus on executing that plan.


