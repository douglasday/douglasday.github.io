---
title: "How I Became The Most Valuable Hacker"
date: 2024-12-13
layout: single
author_profile: true
---


This January, I found myself under Miami’s sun, hacking for Capital One at HackerOne’s H1-305 live hacking event (LHE). Imagine this: 50-100 of the world’s best hackers flown to a fun destination on an all-expenses-paid trip to hunt for bugs, earn bounties, and compete for prizes. What’s not to love? Besides the thrill of free travel, and open bar, and hacking by the pool, what makes these LHE's particular attractive is:

1. Quick bounties - For _most_ of your bugs, you'll see payment while on site
2. In-person back-and-forth with the security team - This is particularly helpful when trying to communicate a particularly complicated bug
3. Expanded Scope - LHE's are a good opportunity for a program to bring in new features/subsidiaries/etc as a trial run before introducing them to their main program
4. Bigger Bounties - It's not uncommon for programs to 2-3x their normal bounty amounts in LHE's. 
5. Networking - Meeting other hackers in person will set up LOADS of opportunities to collaborate in the future. I owe my entire success in the LHE circuit to meeting [Jesse](https://hackerone.com/hogarth45) at Top Golf in Vegas at H1-702-2019
6. Swag - My wife & joke that after 19 LHE's, half of the stuff in my house is Hackerone branded. And as soon as the H1 team releases Hackerone branded boxer-briefs I'll have a full outfit, from shoes to hat. 
   
   
However being a competition, there are also _prizes_ beyond the bounties you receive. Money is great, but trophies look way better on your wall. They're harder to accidentally spend on beer, too.

The trophies are awarded for a number of accomplishments including:
- 1st/2nd/3rd place
- Finding the most impactful bug as a whole
- Finding the best bug on the last day
- etc

But the most coveted prize of all (besides that [damn poster](https://x.com/Hacker0x01/status/1820618661566251191) that I can't ever seem to get) is a WWE-style wrestling belt awarded to the Most Valuable Hacker, or MVH. This belt is awarded to the hacker who provides the highest quality work to the customer in terms of Consistency, Criticality, & Community.

I wanted this belt. I told my wife I was going for it. I told [Twitter](https://x.com/ArchAngelDDay/status/1743440198472745385) that I was going for it. I had been hacking for 5 years at this point and still didn't have a belt. This one was going to be mine. BUT, winning the belt isn't as simple as just finding good bugs. There's some additional skills when it comes to LHE's that I'm about to share with you. 

### Finding Bugs is Easy - Finding Scope is Hard

If you're at the point in your bugbounty career where you're being invited to an LHE, then it's safe to say that you know how to find bugs. That's not enough to set you apart anymore. In order to set yourself apart, you are going be needing to either find more bugs than any other hacker, or find more impressive bugs than any other hacker. In my experience, its _easiest_ to do this by hacking on a piece of scope that less hackers are hacking on. 

At H1-0131, I hacked on a particular app that required having an LLC. This reduced the amount of competition/duplicates from 100ish hackers down to _maybe_ 10. I found 2 non-duped crits on this asset, and finished in 12th.

At H1-702, I found a third party app that was serving content to an in-scope asset, and then tore this app to shreds. I got my largest bounty ever on this asset ($25,000), and placed 2nd. 

At H1-65, I spent my entire time hacking on one subsidiary while everyone else was hacking on the core assets. I placed 10th. 

And at H1-305 in Miami, the asset that I focused on wasn't hidden scope per se. BUT, there were 2 other scope items that looked, and _were_ very vulnerable. I knew that they were going to be hot targets. So I took the road less traveled. I think I was one of maybe 5 hackers hacking on this asset. I had my first ever six-figure event and took 1st place with a plethora of fun price manipulation bugs.

In each of the above examples,  had other hackers been looking at my target, I likely would have duped on several of them, thus significantly reducing my placement on the leaderboard.

**Moral of the Story**: *Figure out where other hackers are going to be hacking, then hack somewhere else that's unique*

### The Program Team Wants You to Succeed

In my intro above, I mention in point `#2` that one of the benefits of participating in a LHE is the back and forth communication with the program team. This is _critical_. The program team has eyes that you don't have, and if you're nice can offer insight & guidance that you don't have outside of the LHE context.

At H1-702 my aforementioned biggest bug was an admin account takeover. One of the keys for this bug to work was knowing a particular employees email address. The program team was able to provide this to me, allowing me to demonstrate my bug quicker, saving me time that I could then spend on further exploits.

At H1-65 I needed to understand how an internal authorization mechanism was processing some weird edge-cases. They were able to look in the code and just tell me. 

And at H1-305, My wacky price manipulation bugs needed someone on the inside to confirm/deny if my purchases were going through. As such, I spent literal hours messaging back & forth with [Plutonian Fern](https://x.com/Plutonian_fern)  as she very helpfully would let me know when my exploits were and were not working. Since my biggest bug required 5+ iterations/trials to actually pull it off, had I not had this help from the inside, I would have needed to send in my first (non working) and been crushed when the team informed me that my exploit didn't work.

The program teams are just as excited to see cool bugs are you are to get paid for them. Work with them, and ask them a LOT of questions & favors. And no, by favors I don't mean severity upgrades. I mean asking for visibility into the backend, or to check to see if an exploit worked, or for the ability to chat with a dev. Early on, I was too afraid/nervous to ask favors. Oh how I wish I could get back in time - the bugs I would have uncovered had I only been bolder.

**Moral of the Story:** *As the program team for favors.*

### Staying On One Target Beats Flitting Around Anyday

In each of the 4 LHEs I attended this year, I found most of my bugs on ONE asset. Bug bounty hunters have said for years that going deep is better than going wide, so I'm somewhat beating a dead horse by even bringing this point up. But context switching is hard, and in a time-boxed event like an LHE, you just don't have time to get up to speed on multiple applications. 

Let's take a typical 2-week long hacking window for an LHE before your focus gets disrupted by travel. That's 10 business days (I like to not hack on the weekends, since that's family/God time). And It usually takes me 2 days exploring an app before I start _really_ finding juicy bugs. So with 10 days of total hacking, and 2 of those spend gearing up on the scope I've selected, that only leaves 8 days for really finding interesting bugs. Why on earth, would I want to sacrifice _another_ 2 days to get up to speed on a second app?!

When I've selected my target, I will most likely stay there for the entirety of the event. Exceptions exist of course, we've all accidentally hacked on an app with barely any functionality, and been dismayed when there weren't many bugs to find. But overall, the advantages to sticking on one app are numerous:
- More time spend going deep
- You get to know the app better than any other hacker, allowing you to find super cool crits late in the event
- Your chance of dupes goes way down
- As a subject matter expert on that app, you can continue to farm it after the LHE.

As I mentioned earlier, at H1-305 there were 2 assets in scope which looked RIPE for the plunder. Particularly for my style of hacking - it was littered with IDORs and privilege escalations. But I know that had I focused on those assets, I'd be just another one of the 50 hackers finding IDORs on it. In order to win MVH, I needed to be finding bugs that _other hackers weren't_. I so ignored the temptation and stayed singularly focused on my target.

**Moral of the Story:** _Pick a good target early and stay there._


### Bonus: Spending Money Makes You Money

Note - I write this last point as a bonus because while it's helpful for lots of LHE's, this one in particular didn't help me win H1-305. 

In LHE's, it's very common for programs to provide you test accounts that have gated access to features that are paywalled. However, this isn't always the case. Sometimes a "Pro" or "Plus" tier subscription is required to get additional features. Unless the price is exorbitant, I will very often throw down my Robinhood Gold card and eat the $20-$100 for extra access, knowing a single Low will make it worth the price.

While I didn't use this strategy for H1-305, I _did_ make a pro account on that third party system at H1-702. This unlocked extra scope that no one else was looking at.

The most I've ever paid for a Pro tier was $1,600. But hey, it got me a $5,000 bounty! And as a bonus, the program refunded me the $1,600 anyway! Worth it.

**Moral of the Story:** *Oftentimes the cost of an upgraded version of a target app is negligible when compared to the amount of bounties the program offers*


### Go Forth And Get Your Belt

Live hacking events are an unmatched opportunity to grow, compete, and connect in the hacking community. You can’t control the scope or other hackers’ skills, but with focus, creativity, and the right strategies, you can tip the odds in your favor—and maybe even take home the belt - afterall, I can't wear more than one at a time ;) Good luck, and happy hacking!


Pax in Christo
