+++
title = 'My favorite apps'
date = 2026-08-13T22:00:00+09:00
draft = false
tags = ['technology']
+++

## Browser

I use [IronFox](https://github.com/ironfox-oss/IronFox) (Android) and [LibreWolf](https://librewolf.net/) (Desktop), both of which are privacy-focused community forks of Firefox. I care about privacy so it's important for me that my browsers have strong anti-tracking features. They support all Firefox extensions.

I've tried Brave for Android once but it lacked some features I wanted, like opening links (triggered by other apps) in private windows, so I ditched it.

## Search Engine

[StartPage](https://www.startpage.com/en/) is nice because it's privacy friendly and as far as I can tell its search quality is the same as Google. While it's run by an ad company, its [privacy policy](https://www.startpage.com/en/privacy-policy/) is clear about it not tracking or profiling. [Privacy Guides](https://www.privacyguides.org/en/search-engines/?h=search#startpage) also recommends it.

But it has one pain point which is that when you leave a search result page open for a while, causing the browser to unload it from memory, and you reopen it, it shows an error and the search query is lost. (I thought this was because of its feature to hide search queries in POST request body, but switching to GET via settings didn't solve the issue.)

Because of this annoyance, I set StartPage as the default search engine only on my phone. On desktop I use [Brave Search](https://search.brave.com/), although its search quality is often bad so I sometimes have to switch to StartPage. I don't use DuckDuckGo because its search accuracy is bad.

I used to use [Kagi](https://kagi.com/), a paid search engine, and I liked it quite a bit, but at some point I decided it wasn't worth the money. The $5/month plan only offered 100 searches, which was way too few for me, so I had to go with the $10 plan. It also had an annoying quirk where it logged me out when I navigated back to its search result page.

## Firefox Extensions

### [uBlock Origin](https://github.com/gorhill/uBlock#ublock-origin)

Blocks ads and trackers. This is arguably one of the open source projects that have the greatest positive impacts on the world's cyber security. Online ads are genuine threats because a lot of criminals use them to trick people into installing malware, phish credentials, etc. Google search has so many of these malicious ads.

### [Sidebery](https://github.com/mbnuqw/sidebery) (Desktop Only)

Tree-style tab organizer. This is a game-changing browser extension. It changes how you use a browser. It's also extremely customizable.

Unfortunately it only supports Firefox (perhaps because Chromium doesn't have API for adding this kind of UI). But it's so good it's worth switching to Firefox just for this. Personally I also have other reasons to use a Firefox-based browser, though.

### [LibRedirect](https://libredirect.manerakai.com/)

This extension is really useful. It allows you to use major social media websites with unofficial UI. Whenever you open a link of a supported site, it automatically redirects you to a community-run frontend website.

This has two advantages: (1) It allows you to use sites that are otherwise unusable without logging in, and (2) it prevents tracking by not directly interacting with the official website. (1) is especially helpful with Twitter because, without an account, you can't even view all replies or full account profiles, which is extremely annoying.

One downside of this extension is that these unofficial frontends usually have a bot protection gate, which increases page load time by a few seconds. But I think it's well worth it.

### [Yomitan](https://github.com/yomidevs/yomitan)

Handy popup dictionary. Fast, supports morphology (like recognizing "says" is "say" in base form). I use it to look up English words.

### [Bitwarden Password Manager](https://bitwarden.com/)

The best free password manager.

## Android Apps

### [Aurora Store](https://github.com/whyorean/AuroraStore)

This allows you to install Google Play apps (only free ones) without logging in. I use this to install all non-open-source apps.

The main benefit is privacy; Google won't know what apps you use. But it also has a potential risk that the developer could go rogue or get compromised and then this app could start injecting malware into apps it downloads. However, you can prevent that by checking the checksums of APK files it installs (you can look up legitimate checksum values online). But I must admit I often get lazy. :D

### [Obtanium](https://obtainium.imranr.dev/)

OSS app installer. Most open source apps release their APK files on GitHub, GitLab, etc., so you paste a repository link in this app and it will handle finding and installing the latest version.

Why not F-Droid? F-Droid builds apps from source code itself so you need to trust F-Droid in addition to the app developers. Also F-Droid is pretty slow to release new app versions.

### [Revanced](https://revanced.app/) / [Morphe](https://morphe.software/)

YouTube app patcher. These apps modify the official YouTube app to add a lot of extra settings to add or remove various features. The best feature is ad-block. I'm extremely glad these projects exist. They are technically really impressive too; they de-compile an APK, apply patches, recompile, and sign, all on your phone.

### [FUTO Keyboard](https://docs.keyboard.futo.tech/)

This is the best open source keyboard app I've found. It focuses on accuracy and has its own engine for swipe typing recognition as well as it own models for text prediction and voice transcription (which is impressive!). The models run on your device so it doesn't need network connection.

The dev even created a [new English keyboard layout](https://futo.tech/blog/swipe-keyboard) optimized for swipe typing. When you try to swipe type, say, "stream" on QWERTY, the trajectory your finger takes is hard to distinguish with that of "steam" because R is between T and E, so the keyboard may recognize it as "steam". So they took a data-driven approach to find the layout that minimizes the frequency of such ambiguity. I want to try this layout some time.

### [LinkSheet](https://github.com/LinkSheet/LinkSheet)

This is a nice quality-of-life utility. It allows you to give more control over what apps handle what links.

Normally if you open a Twitter link and you have Twitter installed, then either the Twitter app or your default browser opens it automatically, depending on your system settings. It doesn't allow you choose the app on the spot. LinkSheet gives you that control. You can configure it to show all compatible apps, or skip the picker and use a pre-configured one. And this can be configured on a per-domain basis.

This is useful, for example, when you don't want to pollute your YouTube recommendation feed by opening a potentially weird video but you want to check it anyway. You can choose to open it in browser. And since I've configured IronFox to open links in private windows, Google won't associate the watching activity with your account.

When you have multiple browser apps installed, you can configure it to only show some of them to reduce visual clutter.

It also has privacy features. I use ClearURLs integration, which automatically clears tracking parameters from URLs. I also used LibRedirect integration initially but I eventually switched to the browser extension version, which I explained above, because I also want to redirect links that are opened from inside my browser (which doesn't trigger LinkSheet).

One annoyance is that the app's settings are somewhat confusing. I struggled to figure out how to unset default handlers.

### [LocalSend](https://localsend.org/)

Nice simple tool to copy-paste text or a file between mobile and PC. It doesn't use cloud storage. Instead the devices talk to each other on the same network.

### [WordWeb](https://play.google.com/store/apps/details?id=com.wordwebsoftware.android.wordweb&hl=en_US)

English dictionary app. This isn't open source but is the best dictionary app I've tried so far. It supports morphology. It has pronunciation labels. It clearly shows part of speech.
