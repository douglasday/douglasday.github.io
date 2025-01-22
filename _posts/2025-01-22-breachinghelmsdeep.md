---
title: "Popping Helm's Deep: How one vulnerability opened up an entire fortress of new scope"
date: 2025-01-22
image: /assets/images/posts/Uruk.png
layout: single
author_profile: true
---

Like any good catholic, I've been obsessed with Lord of the Rings. And like any Lord of the Rings fan, one of my favorite scenes from Peter Jackson's interpretation is the siege of Helm's Deep.

Helms deep, the impenetrable fortress of the Rohirrim, is besieged by the Uruk-hai. Within it's walls, remain the last denizens of Edoras. While naturally the good guys win, King Theoden gives a riveting speech, and the day is saved, yadda yadda _whatever_.I want to focus on the role of this crazy nutter:


![Uruk](/assets/images/posts/Uruk.png)

If you haven't seen the movie (please do), this psychopath is holding a torch and running into a _small, overlooked_ sewage gap in the wall where other Uruk-hai have placed a number mines:

![Mines](/assets/images/posts/Helmsdeep.png)


Putting 2 and 2 together, what happens next is a bit explosive:

![Explosion](/assets/images/posts/boom.png)

After which, the walls of Helms Deep are breached and the defense crumbles, leaving the juicy interior of the fortress to be plundered by the Saruman's army.

So how's that relate to bug bounty? Well, a while back, [Rez0](https://x.com/rez0__) and I were looking at a production web application that we weren't given credentials to. And no, this wasn't a self-signup application. All we had was the root domain. 

Much like the Uruk-hai noticing the small overlooked gap Deeping Wall, Joseph noticed a small overlooked set of credentials in the _javascript_ on one of the pages of the applicaiton. As it turns out, these were administrator credentials which had access to one of the orgs in the application. And much like Helms Deep, what was _behind_ the wall was laughably more insecure than the wall itself. Nearly _every. single. endpoint._ was vulnerable to IDOR. We found at least 3 account takeovers. You could add yourself to other organizations, and trivially delete every user in the application. We effectively owned the app. 

So the next time you're hacking on an app that you don't have credentials for, try to find a small overlooked gap in the wall, and you just might find entirely new untouched scope, ripe for the harvest.


Also, read LOTR. It's good for your soul. 