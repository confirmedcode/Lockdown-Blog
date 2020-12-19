---
title: Apple's "Privacy Nutrition Labels" are a Gift to Scam Apps
---

### "App Privacy" should give users verified information, instead of a false sense of security

With the recent release of iOS 14, Apple enabled a new feature called "App Privacy" (or "[Privacy Nutrition Labels](https://www.seattletimes.com/business/technology/new-from-apple-at-wwdc-hand-washing-alerts-iphone-widgets-and-privacy-nutrition-labels/)") in the App Store, which supposedly shows users what information apps collect, and how that information is used. For example, you might have seen people making fun of the Facebook app's long App Privacy section - like the tweet below:

![MacRumors tweet about Facebook app privacy](/assets/images/macrumortweet.jpg)

This, on the surface, *seems* like a win for consumer privacy.

So why is the App Store's App Privacy actually terrible for user privacy?
### Flaw #1: For popular apps, App Privacy doesn't actually tell us anything we don't already know
At this moment in 2020, the fact that Facebook is bad for privacy is already well-known. There are countless articles, documentaries, and reports about the many ways that Facebook exploits user data. Even Mark Zuckerberg admitted this:

> ![Zuckerberg brags about his users being dumb fucks](https://privacyreview-site-assets.s3.amazonaws.com/images/review/facebookmessenger-infographic.png)

People are only on Facebook because their friends are on it. Nobody *wants* to be on Facebook, everyone *knows* it's horrible for privacy - and so showing users this long App Privacy list doesn't actually change anything.

As a thought experiment for the usefulness of App Privacy, imagine if Facebook changed their App Privacy and wrote that they didn't collect any user information. Of course, nobody would believe them. For well-known apps, App Privacy at best only confirms what users already know.

### Flaw #2: For other apps, App Privacy incentivizes dishonesty because it's self-reported
For apps that aren't as popular, App Privacy is detrimental for privacy, because Apple relies entirely on the app developer to be honest about their privacy practices. This creates bad incentives - it's like asking restaurants to do their own health inspections and provide their own health scores.

Let's say a user is searching for a new email app, and is choosing between two candidates on the App Store. One is created by a dishonest developer who fully intends to sell user emails to as many third parties as they can, and the other is created by an honest developer who only uses anonymized analytics in their app. Here's what happens:

![A table showing the incentive structure that Apple has created with App Privacy.](/assets/images/scamapp.jpg)

In this situation, both the dishonest and the honest email apps collect basic, anonymized analytics. The dishonest app also secretly sells user emails to third parties. The dishonest app, however, writes in their App Privacy that they don't collect or sell *any* data, while the honest app admits that they collect basic analytics data. So a user shopping for apps reads the App Privacy for both apps, decides that they want to "maximize their privacy", and downloads the dishonest app. The end result is that the contents of their emails are sold to third-parties.

Apple doesn't verify any of the App Privacy information that app developers submit - because they *can't*. *There is currently no way for Apple to know what an app does with user data after the data is sent to the app.* But by drumming up hype about "App Privacy" and **calling it equivalent to "Privacy Nutrition Labels", Apple very strongly implies that the privacy information is vetted, when that is absolutely false**.

This results in a nightmare feedback loop: Dishonest apps make more money due to "better" App Privacy, and then use their ill-gotten profits to buy Apple's App Store Search Ads, which allows them to appear first in search results and rope in more downloads and more user data. Sell the user data, rinse and repeat. I previously wrote about the magnitude of top-selling apps doing exactly this on the App Store [here](/2020/11/25/how-to-make-80000.html). The App Store's "scam apps" problem has only gotten worse, and App Privacy will help them seem more legitimate than ever before to unsuspecting users.

### App Store's "App Privacy" takes an old idea and makes it worse
In a nutshell, Apple's App Privacy is amplifying the worst privacy invention ever - the Privacy Policy, aka the "We Pinky-Promise to Not Steal Your Data" document. Privacy Policies are bad not just because they're impossible to enforce and easy to abuse, but also because they're not [legally binding](https://ir.lawnet.fordham.edu/iplj/vol27/iss1/5/), and in the rare case that violations are caught, [the](https://www.abine.com/blog/2012/facebook-privacy-violated-by-new-ads/) [penalties](https://www.theverge.com/2018/4/24/17275994/yahoo-sec-fine-2014-data-breach-35-million) [are](https://uk.reuters.com/article/us-facebook-france/facebook-fined-150000-euros-by-french-data-watchdog-idUKKCN18C10C) [slaps on the wrist](http://www.consumerwatchdog.org/blog/google-ruling-shows-need-do-not-track-and-strong-antitrust-action). Apple's App Privacy repackages the Privacy Policy to make it look more trustworthy with Apple Design™, but fixes none of the inherent flaws with it.

Apple needs a much better approach than totally depending on the honesty of profit-driven app companies. Here are two alternatives that are far better for privacy:

One approach is to ask for *proof* from developers that their privacy claims are actually true - for example, enforcing the [Openly Operated](https://openlyoperated.org) transparency standard, which puts the responsibility on companies to prove their claims before being allowed to access users' personal data. This approach is already working with apps that are serving hundreds of thousands of people daily.

Another approach is to rely on neutral third party reports and reviews, like what [Privacy Review](https://privacyreview.co) does - it's like a Snopes or PolitiFact, but for apps. By involving groups that have no financial interest in the apps, App Privacy can become a source of trustworthy privacy information, and thus weed out app developers that abuse or sell user data, instead of giving them an open, unvetted space to lie.

### Final note

Apple's App Privacy is flawed because it creates a heavily-manipulated *illusion* of transparency, without any of the benefits of true transparency. It gives financial incentives for apps to be more dishonest, and we hope Apple alters their course on this for both the health of the App Store ecosystem, as well as their 1.5 billion users worldwide. In the meantime, we advise that you take App Privacy with a large grain of salt, because it's not at all a dependable indicator of trustworthiness - and may simply indicate an app developer's willingness to lie.
