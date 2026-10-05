<!-- revenuedot:readme:start -->
<p align="center"><a href="https://revenuedot.app"><picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/revenuedot/revenuedot/main/brand/kit/wordmark/revenuedot-lockup-white.svg">
  <img alt="RevenueDot" src="https://raw.githubusercontent.com/revenuedot/revenuedot/main/brand/kit/wordmark/revenuedot-lockup-black.svg" height="40">
</picture></a></p>

# RevenueDot Cordova SDK

This is RevenueDot's MIT fork of RevenueCat's `cordova-plugin-purchases`: the same classes and method names, pointed at a RevenueDot server ([RevenueDot Cloud](https://app.revenuedot.app/signup) at `https://api.revenuedot.app`, or one you host) with RevenueDot's response-signing key built in, and kept in sync with upstream.

[![License: MIT](https://img.shields.io/badge/license-MIT-blue)](LICENSE) [![npm](https://img.shields.io/npm/v/@revenuedot/cordova-plugin-purchases?label=npm)](https://www.npmjs.com/package/@revenuedot/cordova-plugin-purchases) [![Upstream](https://img.shields.io/badge/upstream-RevenueCat%2Fcordova--plugin--purchases_8.2.3-lightgrey)](https://github.com/RevenueCat/cordova-plugin-purchases)

## Install

```sh
cordova plugin add @revenuedot/cordova-plugin-purchases@8.2.3
```
The plugin id stays `cordova-plugin-purchases` and the global stays `Purchases`, so `config.xml` and your code do not change. The native side is RevenueDot's `RevenueDotPurchasesHybridCommon` pod and `app.revenuedot.purchases:purchases-hybrid-common`.

## Configure

```js
document.addEventListener("deviceready", () => {
  // Self-hosted server only: RevenueDot Cloud (https://api.revenuedot.app) is the default.
  Purchases.setProxyURL("https://revenuedot.example.com");
  Purchases.configureWith({ apiKey: device.platform === "iOS" ? "appl_..." : "goog_..." });   // each app's public key
});
```

The fork already trusts RevenueDot's signing key, so no signature or verification setting is needed. Full guide: https://revenuedot.app/docs/sdks/cordova.

## What RevenueDot adds

- **Start free on [RevenueDot Cloud](https://app.revenuedot.app/signup)**: free up to $10,000 a month of tracked revenue, then 0.5%, never more than $999 a month ([pricing](https://revenuedot.app/pricing)).
- **The same REST API and webhook payloads** as RevenueCat, so your backend and integrations keep working ([API reference](https://revenuedot.app/docs/api)).
- **Experiments, targeting and the Customer Center** run from the RevenueDot dashboard on the offerings this plugin fetches ([guides](https://revenuedot.app/docs/guides)).
- **A one-line migration:** point the stock plugin at RevenueDot with `setProxyURL`, or install this fork and drop the line ([migration guide](https://revenuedot.app/docs/migrate)).

## Use with your coding agent

Coding agents can read this repository's docs and code on demand, so they use the right package and imports:

- **Context7:** https://context7.com/revenuedot/cordova-plugin-purchases
- **DeepWiki:** https://deepwiki.com/revenuedot/cordova-plugin-purchases
- **GitMCP:** https://gitmcp.io/revenuedot/cordova-plugin-purchases

## Links

- **Docs for this SDK:** https://revenuedot.app/docs/sdks/cordova
- **Releases and changelog:** https://github.com/revenuedot/cordova-plugin-purchases/releases (tags `<upstream version>-revenuedot`; upstream's changes are in `CHANGELOG.md`)
- **RevenueDot server and dashboard:** https://github.com/revenuedot/revenuedot
- **Fork pipeline (what we change and how upstream is merged):** https://github.com/revenuedot/revenuedot/tree/main/scripts/forks

RevenueDot is not affiliated with RevenueCat, Inc. RevenueCat's copyright notice stays in `LICENSE`; RevenueDot's changes are MIT too.

---

## Upstream README (RevenueCat's, unchanged)
<!-- revenuedot:readme:end -->

> [!WARNING]  
> This library is now deprecated. We suggest using our [Capacitor SDK](https://github.com/revenuecat/purchases-capacitor) instead.
>
> The Cordova SDK will receive maintenance updates, but new RevenueCat features and new major versions will not be made available. Billing Client v7 will be the latest version this SDK will ever support (it won't be updated to v8), which means that Google will not allow updates to your app after August 31st, 2026 [Read more about Google's Billing Client deprecation schedule](https://developer.android.com/google/play/billing/deprecation-faq)

<h3 align="center">😻 In-app Subscriptions Made Easy 😻</h1>

[![Version](https://img.shields.io/npm/v/cordova-plugin-purchases.svg?style=flat)](https://www.npmjs.com/package/cordova-plugin-purchases)
[![License](https://img.shields.io/npm/l/cordova-plugin-purchases.svg?style=flat)](https://www.npmjs.com/package/cordova-plugin-purchases)

## cordova-plugin-purchases

*Purchases* is a client for the [RevenueCat](https://www.revenuecat.com/) subscription and purchase tracking system. It is an open source framework that provides a wrapper around `BillingClient`, `StoreKit` and the RevenueCat backend to make implementing in-app subscriptions easy - receipt validation and status tracking included!

## Features
|   | RevenueCat |
| --- | --- |
✅ | Server-side receipt validation
➡️ | [Webhooks](https://docs.revenuecat.com/docs/webhooks) - enhanced server-to-server communication with events for purchases, renewals, cancellations, and more
🎯 | Subscription status tracking - know whether a user is subscribed whether they're on iOS, Android or web
📊 | Analytics - automatic calculation of metrics like conversion, mrr, and churn
📝 | [Online documentation](https://docs.revenuecat.com/docs) and [SDK Reference](http://revenuecat.github.io/cordova-plugin-purchases-docs) up to date
🔀 | [Integrations](https://www.revenuecat.com/integrations) - over a dozen integrations to easily send purchase data where you need it
💯 | Well maintained - [frequent releases](https://github.com/RevenueCat/cordova-plugin-purchases/releases)
📮 | Great support - [Help Center](https://revenuecat.zendesk.com/)
🤩 | Awesome [new features](https://trello.com/b/RZRnWRbI/revenuecat-product-roadmap)


## Installation
Please follow the [Quickstart Guide](https://docs.revenuecat.com/docs/) for more information on how to use the SDK

### Requirements
*cordova-plugin-purchases* requires Xcode 15+ and minimum targets iOS 13.0+. The minimum Android version compatible is 6.0 (API level 23).

## SDK Reference
Our full SDK reference [can be found here](https://revenuecat.github.io/cordova-plugin-purchases-docs).
