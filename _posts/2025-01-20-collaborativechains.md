---
title: "Report Pointers for Collaborative Chains"
date: 2025-01-20
layout: single
author_profile: true
image: /assets/images/posts/Chain.png
---



As bug bounty hunters, we often find ourselves working on complex vulnerability chains that require multiple components to achieve maximum impact. Sometimes, we'll discover most of a chain but find ourselves missing that _one crucial piece_ that would turn our Medium severity bug into a Critical. 

For example, imagine you've discovered a way to achieve account takeover, but it requires an XSS as an entry point. You know another researcher has already found and reported an XSS that would work perfectly, but they're using that XSS as part of their own larger research project. They don't want to share the technical details of their finding, and you don't want to spend weeks trying to rediscover what they've already found.

### The Solution

I've found a simple yet effective way to handle this situation that benefits both parties: Report Pointers.

Here's how it works:

1. Reach out to the other researcher and explain your chain
2. If they're willing to collaborate, get their report number
3. In your report, simply reference their report number for that step

For example, your report might look like this:

```
Steps to reproduce:

1. Login as user A
2. Navigate to /admin/settings 
3. Modify the following parameters in the request:
   - user_id=1337
   - role=admin
4. Utilize the XSS vulnerability detailed in report #31337 by @other_researcher
5. When the admin clicks the link, their session token will be sent to our endpoint
6. Use the captured session token to access their account
```
### Why This Works

This approach has several benefits:

- The original researcher's work remains protected
- The program gets visibility into how vulnerabilities can chain together
- You get to demonstrate the full impact of your finding
- Both researchers can get proper credit for their contributions

### A Word of Caution

Before using this approach, make sure to:
- Get explicit permission from the other researcher
- Agree on a proper bounty split

### Conclusion

Bug bounty hunting doesn't have to be a purely solo endeavor. By finding ways to collaborate while respecting each other's research, we can uncover more impactful vulnerabilities and create better security outcomes for the programs we hack on.

As always, stay safe & stay metal!

(Report Pointer naming credit to [NBK_2000](https://twitter.com/NBK_2000))


<div class="newsletter-signup">
  <h3>📬 Subscribe to my Newsletter</h3>
  <p>Get the latest security research and bug bounty tips directly in your inbox!</p>
  <a href="https://archangel.beehiiv.com/" class="newsletter-button">
    Subscribe Now
  </a>
</div>

<style>
  .newsletter-signup {
    margin: 3rem 0;
    padding: 2rem;
    background: #f8f9fa;
    border-radius: 8px;
    text-align: center;
    border: 1px solid #e9ecef;
  }

  .newsletter-button {
    display: inline-block;
    padding: 0.8rem 1.5rem;
    background-color: #e67e22;
    color: white;
    text-decoration: none;
    border-radius: 4px;
    font-weight: 600;
    margin-top: 1rem;
    transition: background-color 0.2s ease;
  }

  .newsletter-button:hover {
    background-color: #d35400;
    color: white;
  }
</style>