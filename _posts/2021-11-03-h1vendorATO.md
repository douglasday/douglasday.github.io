---
title: "How I Achieved ATO on an H1 Vendor"
date: 2021-11-03
---

# How I achieved ATO on a HackerOne vendor

Every year as a HackerOne Clear verified researcher, I'm required to register on a couple of vendors that HackerOne uses. As I was going through the process of providing my social security number, 7 years of address history, my mother's maiden name, and last bowel movement, I saw a little familiar popup in the bottom left corner:

<img width="97" alt="Screen Shot 2021-07-21 at 8 03 06 AM" src="https://user-images.githubusercontent.com/31019155/126511743-fe8dd939-979b-4902-af9a-402e6133dbc3.png">


You know those moments when you're trying to kick your Redbull/caffeine addiction by quitting cold turkey but you hear that familiar _KSshhh_ sound of someone opening a can as the sweet smell of your favorite synthetic neon nectar wafts through the air? Yeah, my heart started palpitating like that.

If you're not familiar, that little smiley square is the logo for a _very_ popular chat widget called [Intercom](https://www.intercom.com). This widget is commonly used by salesfolk and support engineers to assist customers.  _Typically_, once you've logged in to the application Intercom uses your session to know who you are. However there's a very important caveat with Intercom that I see misconfigured a LOT. It's called [Identity Verification](https://www.intercom.com/help/en/articles/183-enable-identity-verification-for-web-and-mobile). With Identity Verification, your user session in the application will provide Intercom with a hash. Without that hash, you are not able to interact with Intercom. 

But the misconfiguration I see often is that Identity Verification is never actually enabled. As such, you can just tell Intercom that you're someone else. Yes, you heard that right. For those of you missing your highschool glory days of buying jager with a fake ID, you can effectively do the same in Intercom! Minus the hangover. And the disappointed parents.

Anywho, back to the vendor! Whenever I see Intercom being used on an application, I do a quick check to see if Identity Verification is enabled. The first step to testing this is by logging in as my authenticated user and actually making a conversation:

<img width="359" alt="Screen Shot 2021-07-21 at 8 38 23 AM" src="https://user-images.githubusercontent.com/31019155/126517667-821b67bc-7c52-4118-9fda-7b06f988e4ad.png">

After a quick casual chat with the very friendly bot, I logged out and hit the login page in an incognito window, pulled up my browser's javascript console, and ran the following to just pull up the Intercom widget 

```
Intercom('show');

```

At this point, I am still unauthenticated and Intercom doesn't know who I am. I'm effectively a guest. So I ran the following payload to trick Intercom into thinking I'm someone else:

```
Intercom('boot' {
  email: '<MY_EMAIL_ADDRESS>'
});
```

Upon refreshing the page, I noticed that the Intercom widget changed to the following:

<img width="369" alt="Screen Shot 2021-07-21 at 8 43 06 AM" src="https://user-images.githubusercontent.com/31019155/126518450-66cc6dbe-0551-435a-b8c8-832cc0027718.png">


Aha! That `See all your conversations` wasn't there before!

And yep, before you ask, after clicking that I was provided with my conversation with the support bot from before!

After chuckling for a second to myself like Ray Liotta in _Goodfellas_ , the gravity of what I was seeing started to sink in. This was a vendor that stored my _social security number_, along with basically every piece of information needed to steal my identity. Yikes! I sent a quick note to the very awesome [Jessica](https://twitter.com/sgtcardigan) who told me to report it the the [Hackerone BBP](https://hackerone.com/security)

<img width="684" alt="Screen Shot 2021-07-21 at 8 52 10 AM" src="https://user-images.githubusercontent.com/31019155/126520208-a9965bdf-d61f-4942-a21d-4b4aed1a7e93.png">

Always one to take an opportunity to get on Jobert's good graces, I submitted my report later that night:

<img width="1318" alt="Screen Shot 2021-07-21 at 8 58 00 AM" src="https://user-images.githubusercontent.com/31019155/126520817-0a3d665a-bc72-419c-995e-856350fc7470.png">

After submitting the bug to Hackerone themselves, I went to bed content that I'd helped keep the rest of you hackers safe.

### The juice gets juicier

The next day I went back to the application for fun and I noticed that a non-bot user picked up the chat and was asking me if they could help with anything. Never one to turn down some smalltalk, and wanting to see where this would lead, I responded as vaguely as I could:

<img width="360" alt="Screen Shot 2021-07-21 at 9 07 12 AM" src="https://user-images.githubusercontent.com/31019155/126522235-f19001b7-1727-4b00-b6f2-a7438e36378e.png">


The next response surprised me...

<img width="361" alt="Screen Shot 2021-07-21 at 9 08 58 AM" src="https://user-images.githubusercontent.com/31019155/126522368-18e2b642-cc1c-4aa8-8bb1-dee4e3a223b2.png">

Whoa! Where are they going with this?!

<img width="311" alt="Screen Shot 2021-07-21 at 9 10 34 AM" src="https://user-images.githubusercontent.com/31019155/126522567-cb48fc83-4450-44d9-a85c-465e9831e165.png">


Lolwut. If earlier my heart was beating as fast as a redbull junkie hearing a can opening from across the room, NOW I was more like a redbull junkie hearing a can opening while simultaneously finding a crit on Redbull's [BBP](https://app.intigriti.com/programs/redbull/redbull/detail).  Not only could I view the support conversations and impersonate any other user, but I could also remove their security questions and set their password to `summer@123`. 

![fatality](https://user-images.githubusercontent.com/31019155/126523744-0ccae357-c87b-4c2b-a01f-fb95886f721a.gif)


### The Resolution

After providing the new information in the H1 report, Jobert himself quickly triaged the issue and told me he'd reach out to the vendor's CISO. After a couple of back & forths between Jobert and the CISO, CIO, and Head of Appsec, the issue was quickly patched (both the human element of changing passwords, AND the Intercom misconfiguration):

<img width="1288" alt="Screen Shot 2021-07-21 at 9 25 54 AM" src="https://user-images.githubusercontent.com/31019155/126524715-b451b39d-ffde-4314-aabb-7445fcd41f75.png">

Since you greedy hackers are wondering, no bounty was awarded as they do NOT run a BBP/VDP and awarding me a bounty would set a wrong precedent that other hackers could hunt for vulnerabilities and expect a payment. Such is the life of an ETHICAL hacker :-) Jobert gave me a nice $500 thank-you though. Thanks, bud!

All in all this was a great experience and a pretty cool story to tell. All parties involved were really rockstars here:

- Hackerone was a rockstar for taking my report and being so responsive as we worked with the vendor to get this patched
- `<REDACTED>` was a rockstar for getting the issue resolved so quickly and for being receptive to my report
- The reporter was a rockstar for being the best looking bounty hunter in the industry

As always, stay safe & stay metal!

And if you like this bug:
BTC to `3KvQFALzyUe27kPCBP89wMZDN9uzWHGTEU`
ETH to `0x462EF9726F8d68cC7A3ABedFAE62096C99E3b7A7`
