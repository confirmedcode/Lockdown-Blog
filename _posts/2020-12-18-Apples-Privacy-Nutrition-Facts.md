---
title: Apple's "Privacy Nutrition Labels" are a Blessing and a Curse
---

### "App Privacy" should give users verified information, not a false sense of security
<!--more-->

With the recent release of iOS 14, Apple enabled a new feature called "App Privacy" (or what they call [Privacy Nutrition Labels](https://www.seattletimes.com/business/technology/new-from-apple-at-wwdc-hand-washing-alerts-iphone-widgets-and-privacy-nutrition-labels/)) in the App Store, which supposedly shows users what information apps collect, and how it's used. For example, the Facebook app's extremely long App Privacy section, which details all the information they collect, is already the subject of viral tweets such as this one:

![MacRumors tweet about Facebook app privacy - finger cramping from scrolling so much](/assets/images/macrumortweet.jpg)

Most people are already aware that Facebook has terrible privacy practices, but Apple still deserves a lot of credit for exposing Facebook so publicly on their official platform. Raising awareness about privacy is terrific, and this is definitely the right direction. So what's the catch?

The problem with Apple's App Privacy is that it's entirely self-reported. The app developer gets to make whatever privacy claims they want, and none of that information is vetted. There's no verification by Apple or by any other source.

App Privacy is not new. It's re-branding and simplification of the Privacy Policy, aka the "We Pinky-Promise to Not Steal Your Data" document. Unfortunately, App Privacy doesn't fix the Privacy Policy's inherent and critical flaw: Privacy Policies contain no proof of the privacy claims they make.

Apple doesn't verify any of the App Privacy information that app developers submit - because they *can't*. There is currently no way for Apple to know what an app does with user data after the data is sent to the app. But by calling it equivalent to "Privacy Nutrition Labels", Apple irresponsibly implies that this privacy information is vetted, when that is absolutely false.

This results in two unintended consequences: it creates a false sense of security for users, and an incentive for more dishonest and privacy-invasive apps in the App Store.
### A False Sense of Security for Users
The Privacy Policy, and by extension, App Privacy, has been a failure due to its inaccuracy and lack of reliability. This is partially because even the app developers themselves may not know what user data is being given to third parties, or who those third parties give user data to.

One example of this is a recent privacy scandal involving the [mass selling of user data](https://9to5mac.com/2020/11/20/us-military-buys-location-data-from-muslim-prayer-app-and-more/) to the U.S. military, with location data harvested from various apps - a Craigslist app, a Muslim prayer app, weather apps, and many others. This was possible because these apps used a third-party integration that sold location data. And since the app developer didn't even know the third-party integration was doing this, they of course didn't mention it in their apps' Privacy Policies (or App Privacy) - they can't include what they don't even know.

Another example is the case of poor security practices, resulting in security breaches. It seems like every week, some company "regrettably" announces that [they've been hacked](https://haveibeenpwned.com/PwnedWebsites). Last week, it was SolarWinds, who apparently set their server password to "[solarwinds123](https://www.reuters.com/article/global-cyber-solarwinds/hackers-at-center-of-sprawling-spy-campaign-turned-solarwinds-dominance-against-it-idUSKBN28P2N8)". Negligent, cheap, and lazy security practices like this are commonplace, and are opaque to even the most detailed Privacy Policies.

Both real-world examples above seriously impact user data and privacy, and unfortunately in both cases, App Privacy doesn't help, and worse, may give users a false sense of safety.
### Incentivizing Dishonest and Privacy-Invasive Apps
The App Store ecosystem is a competitive place. For every app, there are at least two or three apps with similar functionality competing for the same users. And you don't need five email apps - you need one good one. Users choose apps based on many factors: features, design, screenshots, reviews, and now with iOS 14, App Privacy. So to win the most users, developers are now incentivized to make their App Privacy look good. Key phrase: "**look** good".

Again, App Privacy is based on Privacy Policies, so it relies on the app developer to be honest - it's like asking restaurants to do their own health inspections and provide their own health scores. Now that App Privacy makes the Privacy Policy much more prominent, how does this affect the incentive structure for App Store apps?

Let's say you're choosing between two email apps on the App Store - both seem similar in features and design. Unbeknownst to you, however, one email app is created by a dishonest developer who intends to extract extra profit by selling your emails to third parties, while the other email app is honest and does not do this. Which app do you end up choosing?

![A table showing the incentive structure that Apple has created with App Privacy.](/assets/images/scamapp.jpg)

In this situation, both email apps collect basic analytics. The dishonest app, however, writes in their App Privacy that they don't collect or sell *any* data, while the honest app admits that they collect basic analytics. So you read the App Privacy for both apps, and decide that since you want to "maximize privacy", you download the dishonest app - the one that secretly sells your emails to third parties. It's not your fault - it's the fault of a poor incentive structure.

This results in a nightmare feedback loop: Dishonest apps make more money due to their willingness to lie on their App Privacy, and then use their ill-gotten profits to buy Apple's App Store Search Ads, which allows them to appear first in search results and rope in more downloads and more user data. Sell the user data, rinse and repeat. I previously wrote about the magnitude of top-selling apps doing exactly this on the App Store [here](/2020/11/25/how-to-make-80000.html). The App Store's "scam apps" problem hasn't gotten better since then, and the introduction of App Privacy will now help them seem even more legitimate than ever before to unsuspecting users.

### Finding Apps That Truly Respect Privacy
So what can be done about App Privacy's ease of abuse?

Apple has said that developers caught lying on their App Privacy will be banned, but this threat has no teeth. First, as mentioned earlier, it's impossible for Apple to catch liars because Apple has no way of knowing if app developers are telling the truth about privacy - this threat is only effective against the most visible companies like Facebook, who are already under heavy scrutiny. Second, Apple is not financially incentivized to eliminate profitable apps from the App Store (since they take 30% of revenues as well as App Store Ads), and other than specific removals of a few scandals that go viral in the media, they aren't spending the time or resources to individually verify the 2 million apps on the App Store.

Luckily, you don't need to depend on Apple. Here how to find and choose truly privacy-respecting apps:

First, look for apps that are 100% open source. Open source is the "organic" of software, and it means the app's code is publicly visible, so there's nothing to hide. There are no unknown third-party integrations, and everything the app does, including collection of data and how it's used, is accessible by everyone. Importantly, ensure that not just the app, but also the app's servers (where your data is stored and transferred in the cloud) are 100% open source.

Second, check a site like [Privacy Review](https://privacyreview.co) for neutral third party analyses on the tracking behaviors of specific apps. Instead of trusting App Store's App Privacy, which is self-reported, these sites use tools like [Lockdown Privacy](https://lockdownprivacy.com) to see exactly what connections to trackers are made - it's like a Snopes, but for apps. Watch out, though, for review sites that get a "referral bonus" from your app signups or downloads - these are almost always scams, because they only get paid when you purchase the app.

Third, make sure that management and ownership of the company is clear. Who is the CEO? Where are they located and are they a real company? Or are they a series of offshore shell companies that allow the owners to stay anonymous? You'll be surprised how often that last one is true, especially for so-called privacy apps that are [malware](https://www.techspot.com/news/60828-popular-free-vpn-service-hola-dodgy.html) or [data-mining](https://9to5mac.com/2017/08/07/hotspot-shield-snooping-on-users-vpn/) companies [in disguise](https://techcrunch.com/2020/12/16/australia-sues-facebook-over-its-use-of-onavo-to-snoop/).

### Final note

Apple's App Privacy creates a heavily-manipulated *illusion* of transparency, without any of the benefits of true transparency. It gives financial incentives for apps to be more dishonest, and Apple would be well-advised to change course on this for the health of the App Store ecosystem and their 1.5 billion customers.

App Privacy has a lot of potential. It shouldn't just be a watered-down Privacy Policy that misleads users. It should instead adopt a verifiable transparency standard like [Openly Operated](https://openlyoperated.org), which puts the responsibility on the companies to prove their security and privacy claims before being allowed to access user data.

In the meantime, we advise that you (and your family and friends) to take App Privacy with a heavy grain of salt, because it's not at all a dependable indicator of trustworthiness - and may simply indicate an app developer's willingness to lie.
