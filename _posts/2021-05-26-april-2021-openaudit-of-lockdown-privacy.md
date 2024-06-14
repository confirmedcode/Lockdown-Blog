---
title: 'Introducing OpenAudit: Forget Privacy Policies, Get Privacy Proof'
---

#### To see exactly what your apps are doing with your data, ask for an OpenAudit.
<!--more-->
<div style="margin-x:auto; text-align:center; margin-top: 10px; margin-bottom: 10px;">
	<img src="/assets/images/oa-logo.png" alt="Logo for OpenAudit. Yellow circle with the word OpenAudit to the right of it.)" style="height: 80px;">
</div>

Apps have a responsibility to protect the privacy of user data, and to secure it against external and internal threats. But apps often just make up whatever privacy claims sounds good, and place it in their marketing materials, Privacy Policy, and Apple's self-reported [Privacy Nutrition Facts](/2020/12/18/Apples-Privacy-Nutrition-Facts.html). This leads to data [hacks, leaks, and even theft](/2020/12/02/why-you-cant-trust.html).

OpenAudit is a standardized way of *proving* these claims, instead of just asserting them. Here is a [simple tutorial](https://openaudit.com/tutorial) on how it works. A claim must have **references** (either specific lines of code, or relevant documentation). Auditors then perform **verifications** on each reference to ensure they adequately support the claim. More relevant to Lockdown Privacy users, we also conducted an [OpenAudit](https://openaudit.com) in April 2021. Here's a snippet:

![Screenshot of a the same text document, but now there is a popover that has 3 citations/proof entries right beneath the text that was previously pointed to. The first proof is a Github code snippet with actual source code, second is the wikipedia entry on Advanced Encryption Standard, and third is another code snippet from Github. Under each entry are two "VERIFIED" labels with the usernames of the security auditors who verified each entry.](/assets/images/oa-2-email.png)

In this example, the reader clicked the claim that "user data [...] is protected by modern encryption", which shows a popup with the proof of that claim: three references that support it, and two auditor verifications per reference. OpenAudit is designed to show everyday users which claims have been independently verified, while allowing technical users to quickly dig into the details. Lockdown Privacy’s OpenAudit has a total of 582 references and 1164 verifications, all publicly viewable at [https://openaudit.com](https://openaudit.com). 

Today, users are forced to blindly trust that their apps (even privacy apps) won't steal or leak their data. But how can you tell which apps actually respect your privacy, and which apps are just using slick marketing and making false promises? In an App Store plagued with fraudulent, scammy, and negligent apps, OpenAudit lets honest apps stand out by earning user trust through independently verified proof.


OpenAudit is [open source](https://github.com/OpenlyOperated) and developers can use it to to audit their own apps for free at [openaudit.com](https://openaudit.com). And if you want to work on this full-time, we're hiring! Reach out to [work@openaudit.com](mailto:work@openaudit.com) to join our mission of using transparency to make apps, services, and the web a safer and more trustworthy place for everyone.
