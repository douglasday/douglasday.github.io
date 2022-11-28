---
title: "Embedded Hackers"
date: 2022-11-28
---

### The History

Since the beginning of Bug Bounty, the triage experience has always been a point of contention. From the program perspective, having a managed triaged service allows you to filter out the noise, and ensure any reports that get to you are valid. From the hacker perspective however, a triage service occasionally feels like an extra step you need to go through to get your report to the program. This isn't to say that triaging is bad for the hackers. In fact, you may find that having a triager read your report serves somewhat as a pair-programmer or [rubber ducky](https://en.wikipedia.org/wiki/Rubber_duck_debugging) to help you _really_ get to the source of your bug. Additionally, for hackers who's second language is English (or whatever the program's primary language is), having a triager is helpful in ensuring the impact of your bug is properly communicated to the program.

This is _not_ meant to be a knock on triaging services. As a program runner myself, they have proved _worth their weight in gold_. And as a hacker, in a couple of cases they've helped to escalate my report (Cheers, `Bluetooth_headset`, `Turtle_shell`, and `NochnoiDozor`). 

The problem that I'm wanting to address is that occasionally you'll have an anchor program that you've been hacking on for many months/years, and have become intimately familiar with their application/stack/tool. Eventually, you'll get to the point where you know the app(s) better than even some of the developers, and when a program sees a report come in from you, they'll _know_ it's valid and quality. For example [Dominic](https://hackerone.com/dee-see) is the top hacker for [Elastic](https://hackerone.com/elastic) (my current employer), and any reports that he files we already know will be high quality. When you gain this level of familiarity, a problem starts to arise with the triaging service. By neccessity, triagers need to be generalists. Hell, they work on literally _hundreds_ of different programs. This means that they will _never_ have as much knowledge of the app(s) as you, and you'll start having to do lots of back-and-forth explaining how \<Insert abstract tech here\> works.


As a hacker, it can be very frustrating needing to keep re-explaining niche peices of functionality/technology to triagers. As a program, it can be frustrating seeing a high/critical report weeks later than I would have normally if the report went straight to me. And I imagine the triagers would rather be cutting down on their queue than needing to have 7 NMI back-and-forths.



### The Solution
  
  People in the Bug Bounty community have long asked for some type of merit system to bypass the triaging experience. This has been problematic for a number of reasons. Namely, no one wants to hack on a platform that's turned into a [Good Ol Boys Club](https://en.wikipedia.org/wiki/Old_boy_network). But additionally, just because a hacker is super proficient hacking Shopify for example, it doesn't mean they'll be knowledgable on the PayPal bug bounty. For these reasons, I don't believe that a platform-wide exemption from triaging will ever work.
  

However, to help programs/hackers out in the situation where there's a hacker who's consistently submitting high quality reports to their program, I'm suggesting something I'm calling the `Embedded Hackers` feature. I know, I'm bad with names. Here's how it would work with a fictitious hacker named `Alex` and a fictitious program called `Angel Warehouse`:
  
Alex is a talented hacker who's been hacking on the `Angel Warehouse` bug bounty program for months. They read all of our documentation, consistently find bugs, and I as the Program Manager know that whenever I see a report from Alex, it's going to be valid. Within my program settings, in a similar way to how I can invite hackers to my program, I can have a list of `Embedded Hackers`. As the Program Manager, I decide to add Alex to my list. The next time that Alex submits a report to the Angel Warehouse program, rather than being auto-assigned to the triaging service, it gets auto-assigned to the Angel Warehouse team with a private message that reads:

```
Hello - this report was filed by a hacker in your Embedded Hackers list, and as such has skipped the triaging service. If you need assistance with this report, please feel free to re-assign this back to the triaging service.
```

`Angel Warehouse` then gets to view and handle the report right away, saving valuable time in the case of a High/Critical report.
  
  
 NOTE - While _yes_ a program could technically just monitor their queue for reports from their consistent hackers, for high-volume programs this becomes unfeasible.
  
 ### How It Benefits The Hacker

 - The hacker has to waste less time explaining the niche functionality that's specific to the program.
 - The hacker gets paid faster

### How It Benefits The Program
  
  - In the case of High/Critical reports, the program gets visibility into the vulnerability faster
  - The program has the agency to curate their _own_ program specific Embedded Hacker list


### How It Benefits The Triager

  - The triager gets to focus on their queue and spend less time learning an obscure peice of technology that they may never use again
  - The triager has to deal with fewer frustrated hackers.


### Conclusion

As mentioned earlier, a platform wide exemption of triage will never work. But having this feature be _program specific_ I think makes a lot of sense and will alleviate pain on all of the stakeholders involved.
  
**Quod Erat Demonstrandum**
