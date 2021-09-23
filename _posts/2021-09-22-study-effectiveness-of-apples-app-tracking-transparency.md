---
title: 'Study: Effectiveness of Apple''s App Tracking Transparency'
author: Johnny Lin and Sean Halloran
---

#### Does it stop third-party tracking? Or is it just an illusion of privacy?
<!--more-->
### Summary
In April 2021, Apple released the App Tracking Transparency ("ATT") feature with iOS 14.5. ATT claims to give users choice and transparency for third-party tracking in their apps, and it was lauded by many as a step forward in protecting user privacy. Does it really work? Five months after its release, we tested ten of the top apps in the App Store to see if ATT succeeds in stopping tracking.

Using the open source [Lockdown Privacy](https://lockdownprivacy.com) app and manual testing, we found that **App Tracking Transparency made no difference in the total number of active third-party trackers, and had a minimal impact on the total number of third-party tracking connection attempts. We further confirmed that detailed personal or device data was being sent to trackers in almost all cases.** ATT was functionally useless in stopping third-party tracking, even when users explicitly choose "Ask App Not To Track".

### Who We Are
We're ex-Apple engineers whose mission is to increase transparency in technology. We've spent the last four years creating open source privacy software ([Lockdown Privacy](https://lockdownprivacy.com)), writing informative content ([Transparency Matters](https://blog.lockdownprivacy.com), [Privacy Review](https://privacyreview.co), [Openly Operated](https://openlyoperated.org)), and building free tools to help developers become more transparent ([OpenAudit](https://openaudit.com/tutorial)).

Unlike most privacy companies that ask users to trust their unproven Privacy Policies, everything we build is open source, so all the results and data in this report can be replicated and verified by anyone with an iOS device. And because we're also Openly Operated, all our claims are fully backed up by source code, infrastructure, and audit trails — verifiable by anyone with an internet connection.
### Background + Objective
It's no secret that Apple tries to brand itself as a privacy-conscious counterpart to its rivals Google and Facebook, whose ad-based businesses are inherently at odds with privacy. This privacy-as-marketing approach sounds great in ads, but in practice, it's often [less-than-honest](https://twitter.com/lockdown_hq/status/1405298060171923462) or can even [be counterproductive](https://www.fastcompany.com/90591586/apple-privacy-nutrition-labels-flaws). In this study, we test the effectiveness of Apple's latest privacy feature: App Tracking Transparency.

App Tracking Transparency claims to give users a choice in allowing or requesting to disallow third-party tracking in apps. The average iOS user will, while using an app, encounter ATT with this dialog:
![The standard ATT dialog with message: "Allow [insert app name here]" to track your activity across other companies' apps and websites?" and two choices "Ask App Not to Track" and "Allow"](https://privacyreview-site-assets.s3.amazonaws.com/images/att-dialog.jpg)

The user's choice will then show up in the Settings app, under Privacy — Tracking:
![Screenshot of the Settings, Privacy, Tracking page, toggle 'Allow Apps to Request to Track' to ON, text "Allow apps to ask to track your activity across other companies' apps and websites. When this is off, all new app tracking requests are automatically denied. Then Doordash shows switch OFF and Facebook shows switch OFF.](https://privacyreview-site-assets.s3.amazonaws.com/images/settings-tracking.jpg)

Since the two screens above are the entirety of what most iOS users are going to see about ATT, we'll use these dialogs as the standard for our study. In the example above, if ATT is working as advertised, this means that for the DoorDash app, "all new app tracking requests are automatically denied" and the user has asked the app to not track their "activity across other companies' apps and websites."

The objective of this study is to measure how well ATT lives up to Apple's own claims, and to answer the question: How effective is App Tracking Transparency at stopping third-party tracking activity?
### Methodology

To test how effective App Tracking Transparency works, we selected ten top ranked apps, most of which were featured by Apple's own App Store Editors under either the Apps or Games tabs. We used [Lockdown Privacy v1.2.4](https://itunes.apple.com/app/apple-store/id1469783711) to detect (and block) third-party trackers, and manual testing for uncovering the actual content being sent. Some manual testing later uncovered more trackers, which were also included in the results.

We enabled the following Block Lists: Amazon Trackers, Data Trackers, Email Trackers, Facebook Trackers, Game Marketing, General Marketing, Google Shopping, Marketing Trackers, Marketing Trackers II, Reporting. The test device was an iPhone XR initially running iOS 14.8. We later re-tested with the final public release of iOS 15 and found that iOS's ATT behavior, tracking data, the number of trackers were identical. Tests were conducted during August and September.

Since Lockdown Privacy is free and open source, all data and results in this can be verified by anyone. Due to app updates and specific usage behaviors, independent verification results may differ slightly — for example, using a test app for a longer period of time will likely result in more tracking activity.

**Test Process**

We tested each app twice: first with choosing ATT's "Ask App Not To Track", and then again with choosing ATT's "Allow \[Tracking\]". In each test, we did a clean signup and basic usage of the app for no more than two minutes. After each test, we recorded what tracking activity was detected in Lockdown Privacy's Block Log, and then reset everything to test the next case.

**Simplified Test Example**

The following is a shortened version of the test process for the Yelp app. It shows a Settings panel that indicates Tracking is toggled off for Yelp, and then launches the Yelp app. Finally, viewing the tracker Block Log in Lockdown Privacy, we document the dozens of tracking attempts by Yelp's third-party trackers that iOS's ATT has allowed.

<div style="width: 100%; text-align: center; margin-bottom: 20px;">
	<video height="450" controls autoplay muted style="display: block; margin-left: auto; margin-right: auto;">
		<source src="https://privacyreview-site-assets.s3.amazonaws.com/images/yelp.mp4" type="video/mp4">
		Your browser does not support the video tag.
	</video>
</div>
### Results + Data
#### Tracking Activity in Top Ranked Apps: ATT On Vs Off
<table style="text-align:center;">
	<tr style="font-weight:600;">
		<td>App</td><td colspan=2>Active Trackers Found</td><td colspan=2>Tracking Attempts<br/>(Signup & Basic Usage)</td>
	</tr>
	<tr style="font-weight: 600;">
		<td></td>
		<td style="padding: 4px 0px"><small>Ask App Not To Track</small></td>
		<td style="padding: 4px 0px"><small>Allow Tracking</small></td>
		<td style="padding: 4px 0px"><small>Ask App Not To Track</small></td>
		<td style="padding: 4px 0px"><small>Allow Tracking</small></td>
	</tr>
	<tr>
		<td style="padding: 0px 4px;"><strong>Yelp</strong><br/><small>v12.19.0</small><br/><small><strong>#4 Food & Drink</strong></small></td>
		<td>
			<ul style="text-align: left; margin-bottom: 0px; font-size: 0.85em; margin-left: 18px;">
				<li>Facebook Graph</li>
				<li>Bugsnag</li>
				<li>Comscore</li>
				<li>Branch</li>
				<li>Appboy</li>
				<li>Adjust</li>
			</ul>
		</td>
		<td>
			<ul style="text-align: left; margin-bottom: 0px; font-size: 0.85em; margin-left: 18px;">
				<li>Facebook Graph</li>
				<li>Bugsnag</li>
				<li>Comscore</li>
				<li>Branch</li>
				<li>Appboy</li>
				<li>Adjust</li>
			</ul>
		</td>
		<td>39</td>
		<td>42</td>
	</tr>
	<tr>
		<td style="padding: 8px 4px;"><strong>Telegram</strong><br/><small>v7.8.4</small><br/><small><strong>#5 Social Networking</strong></small></td>
		<td colspan=2 style="margin-bottom: 0px; font-size: 0.85em; margin-left: 18px;">
			No Trackers Found
		</td>
		<td colspan=2>0</td>
	</tr>
	<tr>
		<td style="padding: 0px 4px;"><strong>Grubhub</strong><br/><small>v2021.28</small><br/><small><strong>#7 Food & Drink</strong></small></td>
		<td>
			<ul style="text-align: left; margin-bottom: 0px; font-size: 0.85em; margin-left: 18px;">
				<li>Facebook Graph</li>
				<li>New Relic</li>
				<li>Branch</li>
				<li>Google Analytics</li>
				<li>Braze</li>
				<li>AppsFlyer</li>
			</ul>
		</td>
		<td>
			<ul style="text-align: left; margin-bottom: 0px; font-size: 0.85em; margin-left: 18px;">
				<li>Facebook Graph</li>
				<li>New Relic</li>
				<li>Branch</li>
				<li>Google Analytics</li>
				<li>Braze</li>
				<li>AppsFlyer</li>
			</ul>
		</td>
		<td>222</td>
		<td>302</td>
	</tr>
	<tr>
		<td style="padding: 0px 4px;"><strong>Run Rich 3D</strong><br/><small>v1.5.4</small><br/><small><strong>#1 Simulation</strong></small></td>
		<td style="text-align:left;">
			<ul style="text-align: left; margin-bottom: 0px; font-size: 0.85em; margin-left: 18px;">
				<li>Vungle</li>
				<li>Google Analytics</li>
				<li>Mopub</li>
				<li>Applovin</li>
				<li>Google Ads</li>
				<li>Chartboost</li>
				<li>Adjust</li>
			</ul>
		</td>
		<td>
			<ul style="text-align: left; margin-bottom: 0px; font-size: 0.85em; margin-left: 18px;">
				<li>Vungle</li>
				<li>Google Analytics</li>
				<li>Mopub</li>
				<li>Applovin</li>
				<li>Google Ads</li>
				<li>Chartboost</li>
				<li>Adjust</li>
			</ul>
		</td>
		<td>53</td>
		<td>53</td>
	</tr>
	<tr>
		<td style="padding: 0px 4px;"><strong>Starbucks</strong><br/><small>v6.10</small><br/><small><strong>#5 Food & Drink</strong></small></td>
		<td colspan=2 style="text-align:left;">
			<ul style="text-align: left; margin-bottom: 0px; font-size: 0.85em; margin-left: 18px;">
				<li>Branch</li>
				<li>New Relic</li>
				<li>Google Analytics</li>
			</ul>
			<small><i>App Did Not Ask For Tracking Permission</i></small>
		</td>
		<td colspan=2>
			21
		</td>
	</tr>
	<tr>
		<td style="padding: 0px 4px;"><strong>Streamer Life!</strong><br/><small>v1.1</small><br/><small><strong>#1 RPG</strong></small></td>
		<td style="text-align:left;">
			<ul style="text-align: left; margin-bottom: 0px; font-size: 0.85em; margin-left: 18px;">
				<li>Mobvista</li>
				<li>Applovin</li>
				<li>Vungle</li>
				<li>Ironsource</li>
				<li>Mopub</li>
				<li>Facebook Graph</li>
				<li>Google Ads</li>
				<li>Chartboost</li>
				<li>Adjust</li>
			</ul>
		</td>
		<td>
			<ul style="text-align: left; margin-bottom: 0px; font-size: 0.85em; margin-left: 18px;">
				<li>Mobvista</li>
				<li>Applovin</li>
				<li>Vungle</li>
				<li>Ironsource</li>
				<li>Mopub</li>
				<li>Facebook Graph</li>
				<li>Google Ads</li>
				<li>Chartboost</li>
				<li>Adjust</li>
			</ul>
		</td>
		<td>169</td>
		<td>144</td>
	</tr>
	<tr>
		<td style="padding: 8px 4px;"><strong>Subway Surfers</strong><br/>
			<small>v2.20.3</small><br/>
			<small><strong>#5 Action</strong></small>
		</td>
		<td style="text-align:left;">
			<ul style="text-align: left; margin-bottom: 0px; font-size: 0.85em; margin-left: 18px;">
				<li>Facebook Graph</li>
				<li>Ironsource</li>
				<li>Google Firebase Analytics</li>
				<li>Vungle</li>
				<li>AppLovin</li>
				<li>Chartboost</li>
			</ul>
		</td>
		<td>
			<ul style="text-align: left; margin-bottom: 0px; font-size: 0.85em; margin-left: 18px;">
				<li>Facebook Graph</li>
				<li>Ironsource</li>
				<li>Google Firebase Analytics</li>
				<li>Vungle</li>
				<li>AppLovin</li>
				<li>Chartboost</li>
			</ul>
		</td>
		<td>42</td>
		<td>41</td>
	</tr>
	<tr>
		<td style="padding: 0px;"><strong>Cash App</strong><br/>
			<small>v3.44</small><br/>
			<small><strong>#1 Finance</strong></small>
		</td>
		<td colspan=2 style="text-align:left;">
			<ul style="text-align: left; margin-bottom: 0px; font-size: 0.85em; margin-left: 18px;">
				<li>Google Analytics</li>
				<li>Bugsnag</li>
				<li>AppsFlyer</li>
			</ul>
			<small><i>App Did Not Ask For Tracking Permission</i></small>
		</td>
		<td colspan=2>25</td>
	</tr>
	<tr>
		<td style="padding: 8px 4px;"><strong>DoorDash</strong><br/>
			<small>v4.46.1</small><br/>
			<small><strong>#1 Food & Drink</strong></small>
		</td>
		<td style="text-align:left;">
			<ul style="text-align: left; margin-bottom: 0px; font-size: 0.85em; margin-left: 18px;">
				<li>Google Firebase Analytics</li>
				<li>New Relic</li>
				<li>Segment</li>
				<li>Facebook Graph</li>
				<li>Adjust</li>
				<li>Amplitude</li>
			</ul>
		</td>
		<td>
			<ul style="text-align: left; margin-bottom: 0px; font-size: 0.85em; margin-left: 18px;">
				<li>Google Firebase Analytics</li>
				<li>New Relic</li>
				<li>Segment</li>
				<li>Facebook Graph</li>
				<li>Adjust</li>
				<li>Amplitude</li>
			</ul>
		</td>
		<td>170</td>
		<td>168</td>
	</tr>
	<tr>
		<td style="padding: 0px;"><strong>Peacock TV</strong><br/><small>v2.7.10</small><br/>
			<small><strong>#3 Entertainment</strong></small>
		</td>
		<td style="text-align:left;">
			<ul style="text-align: left; margin-bottom: 0px; font-size: 0.85em; margin-left: 18px;">
				<li>New Relic</li>
				<li>Comscore</li>
				<li>Kochava</li>
				<li>Google Analytics</li>
			</ul>
		</td>
		<td>
			<ul style="text-align: left; margin-bottom: 0px; font-size: 0.85em; margin-left: 18px;">
				<li>New Relic</li>
				<li>Comscore</li>
				<li>Kochava</li>
				<li>Google Analytics</li>
			</ul>
		</td>
		<td>15</td>
		<td>57</td>
	</tr>
</table>

#### Total Tracking Activity: ATT On Vs Off

<table style="text-align:center;">
	<tr style="font-weight:600;">
		<td></td>
		<td>Total Active Trackers Found</td>
		<td>Total Tracking Attempts</td>
	</tr>
	<tr>
		<td style="padding: 0px 8px;font-weight:600;">Ask App Not To Track</td>
		<td>50</td>
		<td>756</td>
	</tr>
	<tr>
		<td style="padding: 0px 8px;font-weight:600;">Allow Tracking</td>
		<td>50</td>
		<td>853</td>
	</tr>
	<tr>
		<td>Difference</td>
		<td style="color: red">No Difference In Total Active Trackers<br/>When Asking App Not To Track</td>
		<td>97 Fewer Attempts (~13%)<br/>When Asking App Not To Track</td>
	</tr>
	</table>


#### What Data Is Being Sent To Trackers?
There were a significant number of connections to third parties. Blocking these connections did not affect the functionality of the apps being used, so we looked into what data was being sent. In this section, we highlight the most notable examples. In all cases below, the test chose "Ask App Not To Track" in the ATT dialog.

Note that in all cases, the user's IP address is exposed to the third party, because that is a basic requirement of making a connection to any site or server on the internet. Particularly personal or egregious data being sent are marked <span style="color: red;">in red</span>.

<table  style="text-align:center;">
	<tr style="font-weight:600;">
		<td>App</td><td>Tracker</td><td>Data Sent To Tracker</td>
	</tr>
	<tr>
		<td><strong>Grubhub</strong></td>
		<td>
			<strong><a href="https://braze.com">Braze</a></strong>
			<br/>
			<i>Marketing</i>
		</td>
		<td>
			<ul style="text-align: left; margin-bottom: 0px; font-size: 0.85em; margin-left: 18px;">
				<li style="color: red;">First Name</li>
				<li style="color: red;">Last Name</li>
				<li style="color: red;">Location (Exact Long/Lat)</li>
				<li>Cellular Carrier Name (E.g, "AT&T")</li>
				<li>Screen Resolution</li>
				<li>User Locale</li>
				<li>Time Zone</li>
				<li>iPhone Model</li>
				<li>iOS Version</li>
				<li>Behavioral (Taps, Page Views)</li>
			</ul>
		</td>
	</tr>
  <tr>
    <td><strong>Subway Surfers</strong></td>
    <td>
      <strong><a href="https://vungle.com">Vungle</a></strong>
      <br/>
      <i>Ad Network</i>
    </td>
    <td>
      <ul style="text-align: left; margin-bottom: 0px; font-size: 0.85em; margin-left: 18px;">
				<li>Cellular Carrier Name (E.g, "AT&T")</li> 
				<li style="color: red;">Free Storage Space (bytes precision)</li>
				<li style="color: red;">Current Battery Level (15 decimals precision)</li>
				<li style="color: red;">Current Volume Level (3 decimals precision)</li>
				<li>Time Zone</li>
				<li>User Locale</li>
				<li style="color: red;">Battery Charging State (E.g, "Plugged In")</li>
				<li>Connection Type (E.g, "Cellular")</li>
				<li>Connection Type Detail (e.g, "LTE")</li>
				<li>iPhone Model (E.g, "iPhone X")</li>
				<li>iOS Version</li>
				<li>Language</li>
				<li>User Agent (Browser Agent)</li>
				<li>Screen Resolution</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td><strong>Run Rich 3D</strong></td>
    <td>
      <strong><a href="https://chartboost.com">Chartboost</a></strong>
      <br/>
      <i>Ad Network</i>
    </td>
    <td>
      <ul style="text-align: left; margin-bottom: 0px; font-size: 0.85em; margin-left: 18px;">
				<li style="color: red;">Device Name (e.g, "John's iPhone X")</li> 
				<li style="color: red;">Accessibility Setting: Bold Text</li> 
				<li style="color: red;">Accessibility Setting: Custom Text Size</li> 
				<li>Display Setting: Dark Mode</li>
				<li>Screen Resolution</li>
				<li>Time Zone</li>
				<li>Total Storage Space (bytes precision)</li>
				<li style="color: red;">Free Storage Space (bytes precision)</li>
				<li>Currency (e.g, "USD")</li>
				<li>iOS Version</li>
				<li style="color: red;">Audio Output (e.g, "Speakerphone"/"Bluetooth")</li>
				<li style="color: red;">Audio Input (e.g, "iPhone Microphone")</li>
				<li style="color: red;">Accessibility Setting: Closed Captioning</li>
				<li>Country</li>
				<li>Cellular Carrier Name (E.g, "AT&T")</li>
				<li>Cellular Carrier Country</li>
				<li style="font-weight: 600; color: red;">Last Restart Time (Exact Timestamp, Second Precision)</li>
				<li style="color: red;">Calendar Type (E.g, "Gregorian")</li>
				<li style="color: red;">Enabled Keyboards (E.g, "English, Emoji, Arabic")</li>
				<li style="color: red;">Current Battery Level (15 decimals precision)</li>
				<li style="color: red;">Current Volume Level (3 decimals precision)</li>
				<li style="color: red;">Accessibility Setting: Increase Contrast</li>
				<li style="color: red;">Current Screen Brightness (15 decimals precision)</li>
				<li>Portrait/Landscape Mode</li>
				<li style="color: red;">Battery Charging State (E.g, "Plugged In")</li>
				<li>iPhone Model (E.g, "iPhone X")</li>
				<li>Language</li>
				<li>User Agent (Browser Agent)</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td><strong>Cash App, Grubhub</strong></td>
    <td>
      <strong><a href="https://appsflyer.com">AppsFlyer</a></strong>
      <br/>
      <i>Marketing</i>
    </td>
    <td>
      <ul style="text-align: left; margin-bottom: 0px; font-size: 0.85em; margin-left: 18px;">
				<li style="color: red;"><strong>All data sent by this tracker was encrypted, and the client SDK is closed source. There is no way to determine how much personal user data is being sent to AppsFlyer.</strong></li>
      </ul>
    </td>
  </tr>
</table>
## Discussion 			
In our tests of ten top-ranked apps, we found no meaningful difference in third-party tracking activity when choosing App Tracking Transparency's "Ask App Not To Track". The number of active third-party trackers was identical regardless of a user's ATT choice, and the number tracking attempts was only slightly (~13%) lower when the user chose "Ask App Not To Track".

How do these results compare to Apple's App Tracking Transparency claims? In our earlier section, we observed that the average iOS user will see ATT's claims that "all new app tracking requests are automatically denied" and that a user can ask the app to not track their "activity across other companies' apps and websites."

Neither of Apple's claims about App Tracking Transparency hold up. New app tracking requests were _not_ automatically denied, and even though it is technically correct that the user can _ask_ apps to not track their activity across other companies' apps and websites, in our tests, in no case did apps respect this request. And since every connection exposes the user's IP address, it's trivial for these third parties to uniquely identify users, rendering ATT useless.

In many cases, trackers received much more than the user's IP address. We observed that they received an egregious amount of data, including a user's accessibility settings, the exact time that the user last restarted the device (down to the second), the device's current battery level and screen brightness (both with a precision of 15 decimals), the user's exact latitude and longitude, installed keyboards, time zone, current speaker and microphone settings, currency, volume level, and much much more — see the "What data is being sent to trackers?" section above for full examples.
### Apple's Massive Loophole: A Narrow Definition of Tracking
How could Apple have failed so miserably in stopping third party trackers with a feature named "App Tracking Transparency"? Digging into the answers for this question led us to discover the main cause: Apple's narrow definition of the term "tracking".

In a way, the definition of tracking _can_ be simple and intuitive: Tracking is when an app unnecessarily sends your data to third parties. That third party has now tracked you, because they have, at a minimum, your IP address: the simplest and oldest identifier on the web. From your IP address, your location can be approximated fairly reliably, along with who your ISP is. And since it's an identifier that stays the same for most home internet connections, it's a pretty easy way to track you across the web.

Instead, Apple has hijacked the term "tracking" to define it as something highly specific, and they've even placed their full definition of it in developer documentation, which of course no average iOS user will ever read. So what is it? It turns out that Apple interpretation of "tracking" is that it must fulfill *all* of these conditions: First, it must link user data from one app/website to another app/website. Second, it must do this specifically for targeted advertising or advertising measurement purposes. Third, Apple excludes a list of so-called acceptable tracking behaviors that are not considered "tracking".

Based on our research, we found Apple's definition of tracking to be misleading, counterintuitive, and confusing for these reasons:

1) __It is too narrow in scope__: There are obvious cases outside of advertising where a reasonable person would consider a behavior "tracking". For example, *if someone was tracking your location in real-time using spyware embedded in an app, Apple would not consider this "tracking", because it is not "advertising" related.* 

2) __It contains too many caveats__: Buried in developer documentation, Apple maintains a list of tracking behaviors that are not considered "tracking". While these exceptions might _sound_ reasonable, most of them are vague enough that they can be reinterpreted by even the most egregious trackers to fit in these exclusions. For example, since "fraud detection" is such an expansive exception, marketing trackers can (and do) claim that they are sending dozens of different signals and data from a user's device, not to uniquely identify the user for advertising, but for the purposes of so-called "fraud detection". In fact, during our research, we found a case where a third party's software (Kochava) labeled itself "AppleTracker", even though Apple definition would not consider it "tracking".

3) __It relies too heavily on trusting the very tracking companies that the policies are supposed to be protecting users against__: Apple's definition allows apps to secretly send any and all of your data to third parties, and as long as those third parties _publicly claim_ they won't link your data to other sites or sell it, it's not considered "tracking" by Apple. It is a 100% trust-based honor system, which means that the only way for these companies to get caught "tracking" is to literally pen a public confession of guilt or wrongdoing — something that profit-driven companies are not exactly known for doing. 

4) __It incentivizes less transparency, creating more dangers for privacy__: Apple's tracking definition makes the privacy-regressive assumption that third-party connections are by default innocuous, so any enforcement would require that someone provides definitive proof of abuse. But what if these third-party connections are intentionally obscured or encrypted? Our testing found that Apple allows the closed-source AppsFlyer tracker to encrypt the data that it sends from the user's device, so that nobody can see exactly what AppsFlyer is receiving. The danger here is that third party trackers can access anything that its host app can access. For example, for Square's Cash App, as unlikely as it may sound, it's entirely possible that their embedded AppsFlyer tracker is sending all of your financial transactions to their own third party servers, and nobody other than AppsFlyer — _not even Apple_ — would know.

### To Catch A Tracker, We Must Think Like A Tracker 
But what if Apple is right to trust third-party tracking companies, and all the tracking companies _really are_ trying their best to protect user privacy, even at the expense of their own profits? To test this theory, we "went undercover" by spending a few hours as an app developer who wanted to circumvent Apple's own tracking rules when users choose ATT's "Ask App Not To Track". Would the tracking services allow us to do this, or would we be proven right?

It turns out, we weren't wrong. We were actually more right than we thought.

Not only do these trackers _allow_ their clients to break Apple's rules, but they __specifically built features to help their clients easily circumvent Apple's ATT privacy rules__. 

First, we created a dummy app that used the Kochava tracking service. With just a few clicks, we configured Kochava to violate Apple's "ATT Opt-Out" by asking it to tracking users across apps (using "IP address" and "User Agent") for the purpose of ad targeting ("Paid Media"). Basically, Kochava made it really convenient for any app developer to violate even Apple's narrow definition of tracking.
![Screenshot of our dummy app's settings in Kochava, showing that we configured it to explicitly violate Apple's ATT rules.](https://privacyreview-site-assets.s3.amazonaws.com/images/Kochava.jpg)

We later performed the same test with the AppsFlyer tracking service (which, as previously mentioned, hides the data it sends off your device), and it was _even easier_ to enable "privacy cheat mode" and track users against their consent — all it took was clicking a single button.

![Screenshot of equivalent situation in AppsFlyer, showing it's only one button to turn off user privacy.](https://privacyreview-site-assets.s3.amazonaws.com/images/IMG_3093.png)

It's important to note that since these "cheat ATT" settings are configured on the third party tracker's dashboard, there is a zero percent chance of Apple finding out that apps are engaging in this behavior, because Apple does not have access to it. _Achievement unlocked: Illusion of User Privacy._
## Conclusion
When it comes to stopping third-party trackers, App Tracking Transparency is a dud. Worse, giving users the option to tap an "Ask App Not To Track" button may even give users a false sense of privacy: users who would have otherwise been more cautious with giving their data to an app might let their guard down, thinking that they're "safe" from third-party tracking.  Furthermore, we found that some apps didn't even bother to show the ATT dialog, despite contacting numerous third-party trackers.

The core problem is that App Tracking Transparency is entirely based on the honor system, so it suffers the [same fatal flaw as Apple's "Privacy Nutrition Facts"](https://www.fastcompany.com/90591586/apple-privacy-nutrition-labels-flaws). App developers can choose whether or not to be honest about tracking, and if all their competitors are lying, why would they choose to be honest? Since the App Store has millions of apps, slipping by the rules is not only easy, but as our testing showed, it's the norm.

Apple also doesn't have an incentive to police the very profitable App Store (~20% of revenue). Sure, they'll shut down [no-name scams when they go viral](/2020/11/25/how-to-make-80000.html), or apps that [publicly tout rule violations](https://en.wikipedia.org/wiki/Epic_Games_v._Apple). But what are the odds that Apple reprimands Yelp (partnership with Apple Maps), or DoorDash (#1 Food Delivery App), or popular games ([98% of App Store revenue](https://twitter.com/rjonesy/status/1436372845458771969))? And with enough users, apps can even gain power over the "walled garden", lest their users switch to Android or Huawei. For example, WeChat was [allowed to violate](https://reclaimthenet.org/apple-app-store-wechat-china/) rules because China is a critical market for Apple, and [Uber was given a unique privilege](https://www.techspot.com/news/71289-apple-granted-uber-ios-app-entitlement-allowed-record.html) that let it record users' screens.

So what should Apple do?

Trackers can't send data that they don't have access to, so the most direct technical fix is to limit or eliminate app access to information that is used to [fingerprint devices](https://ssd.eff.org/en/module/what-fingerprinting). In iOS 15, apps are allowed unlimited access to device data that are totally irrelevant to their functionality. For example, why would any app need access to the [exact](https://developer.apple.com/forums/thread/101874?answerId=309633022#309633022) [second](https://web.archive.org/web/20210118025402/https://developer.apple.com/forums/thread/101874?answerId=309633022#309633022) that the user last restarted their iPhone? And why does iOS give apps access to this data in such a high degree of precision? Data such as an iPhone's [remaining battery](https://developer.apple.com/documentation/uikit/uidevice/1620042-batterylevel) and [screen brightness](https://developer.apple.com/documentation/uikit/uiscreen/1617830-brightness) (both accurate to [15 decimals](https://developer.apple.com/documentation/coregraphics/cgfloat)), or an iPad's [remaining free space](https://developer.apple.com/documentation/foundation/nsfilesystemfreesize) (down to the byte), serve no legitimate, [non-fingerprinting purpose](https://nshipster.com/device-identifiers/) for most apps. And for the rare app that might need this level of precision, App Review should approve the usage on a case-by-case basis. 

Apple also needs to take a hard line against closed-source trackers — especially the ones that further encrypt the data they're sending to third-party servers. Trackers have access to everything its host app has access to: Trackers in your finance app have access to all your financial data, trackers in health apps have access to all your health data, and trackers in your photos apps have access to all your photos. And the only way to ensure the tracker isn't stealing any of this, is for the tracker to reveal their source code. Without that, the "walled garden" concept is a total sham, because even Apple's App Review team has zero visibility into what data is being sent to third parties.

On the marketing and user interface side, Apple needs to come clean that App Tracking Transparency is a completely trust-based system, and possibly even rename the feature itself. It's plain dishonest to show users a dialog that gives the option of choosing "Ask App Not To Track", while Apple (a company that excels in user interface and design) knows full well that 1) the average user will be misled into thinking they're protected from tracking and that 2) in practice, there is very little to no compliance or effect on third-party tracking.

In the Settings app, Apple needs to be extremely clear that iOS currently does not and cannot stop third-party tracking. Before iOS 14.5, every app permission (Camera, Contacts, etc) in the Privacy panel has always been enforced by iOS, ensuring that certain apps can or can't access certain features. iOS 14.5's Tracking permission breaks this ten-year-old iOS pattern and misleads users into thinking that it's enforced like every other permission. In fact, iOS even claims something completely untrue here: that "new app tracking requests are automatically denied."

Finally, over the long term, Apple should be more transparent and model transparency for developers by open sourcing not only their software, but also their processes. What _exactly_ does Apple or any app developer do with a user's data when it's uploaded to the cloud? What trackers are embedded in an app? How does Apple's App Review verify an app's privacy promises?

In a world where software and processes are truly transparent, these and other pressing privacy questions can be answered accurately and verified easily. Absent that, a billion iPhone users around the world are stuck with an unacceptable compromise: relying on independent researchers to, in their spare time, test and report on the effectiveness of a trillion dollar company's flagship features.

<br/>
<br/>
