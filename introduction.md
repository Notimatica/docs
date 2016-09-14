# Intro

Notimatica is fast and reliable web push notification service. We make it easy to start sending notifications for engaging and retaining users on your website. We provide JavaScript SDK, server API, and a dashboard for sending messages. Once the setup is done, Notimatica is a delight.

{.toc}
1. [Why use Notimatica?](#why-use-notimatica)
1. [What are web push notifications?](#what-are-web-push-notifications)
1. [Which browsers support web push Technology?](#browsers-support)
1. [What is the difference between push notifications in Chrome, Firefox and Safari?](#browsers-difference)
1. [What are the advantages of web push Notifications?](#web-push-advantages)
1. [How to get started?](#how-to-get-started)

{#why-use-notimatica}
## Why use Notimatica?

* Notimatica provides a full-featured UI and an easy-to-integrate SDK to deliver web push notifications across Chrome, Safari and Firefox.

* Notimatica provides marketing tools including scheduled delivery, targeting, tagging, user segments, multi-language and conversion tracking stats.

* Sure, you can create your own interfaces for GCM and APN protocols, but it ain't easy. There are some open-source projects which can help you, but even the best fail with high volumes (more than 100,000 messages at a time). Also GCM and APN change frequently (Thank you Google and Apple!).

{#what-are-web-push-notifications}
## What are Web Push Notifications?

Web push notification probably is the best thing in the Web since the the invention of hyperlink. These are messages that come from a website. User sees them on a desktop even when the website is not open in a browser. It is a great new marketing tool to engage and retain users on a website without getting their email or other contact details.

Here are most common use cases for web push notifications:

* a business notifies customers about special offers
* a notification is sent when an event occurred (task or job is finished)
* a mass-media website notifies subscribers about breaking news
* a blog notifies subscribers when a new article has been published

{#browsers-support}
## Which browsers provide support for web push notifications?

Web push notifications are currently supported by:

* **Google Chrome**: Version 42+ on Windows, Android, Mac OS X, and Linux. Not supported on iOS.
* **Mozilla Firefox**: Version 44+. on Windows, Android, Mac OS X, and Linux. Not supported on iOS or mobile Firefox.
* **Apple Safari**: Version 7.1+ on desktop Mac OS X only. Not supported on iOS.
* **Microsoft Edge / Internet Explorer:** Not supported
* **Opera:** Not supported

<div class="callout callout-info" role="alert">

#### Please Note
Push notifications are not supported in Private Browsing mode, Incognito mode, Guest browsing mode and Full-screen mode. 

</div>

{#browsers-difference}
## How do push notifications look like in Chrome, Firefox and Safari?

![Push Structure](/static/intro/push_structure.png "Push Structure"){.center-block}

Web push notifications have a bit different outlook from browser to browser and different character limits on tilte and body.

|   | Chrome  | Firefox | Safari |
|---|:----------------:|:---------------:|:-------:|:------:|
| **Title limit** | 70 | 35 | 35 |
| **Body limit** | 115 | 35 | 85 |

### Chrome
Chrome offers the most complete user experience for web push notifications to date with the largest title and body limits. Here is an examples of how the push appears in Chrome on desktop.
 
![Google Chrome Push](/static/intro/chrome_push.png "Google Chrome Push"){.center-block}

**Title**: 70 characters
**Body**: 115 characters

### Firefox

Firefox only supports desktop web push notifications with very limited title and body texts. If the percentage of Firefox users is high among your customer base, then try to keep your messages brief.

![Mozilla Firefox Push](/static/intro/ff_push.png "Mozilla Firefox Push"){.center-block}

**Title**: 35 characters
**Body**: 35 characters

### Safari
Safari supports web push notifications only on desktop. It displays them as native Mac OS push notifications both in the right corner of a screen and as an item in Notification Center.

![Apple Safari Push](/static/intro/safari_push.png "Apple Safari Push"){.center-block}

**Title**: 35 characters
**Body**: 85 characters

<!--Notifications in **Chrome** and **Firefox** are displayed inside browser window. -->

{#web-push-advantages}
## What are the advantages of web push notifications?

{.step-text}
* ##### High user reach

  Chrome, Firefox and Safari altogether have **92% market share**. All of them is providing support for push notifications. This means that you will have almost absolute user reach.

* ##### Ability to re-engage users who are not on your website

  Want to re-engage with users which didn't show-up for a while? With web push notifications you can reach out all off them.

* ##### Ability to sent notification without knowing contact details

  To send a web push you don't need to know user's email or other contact details.

* ##### High acceptance

  Since web push notifications help to protect user's privacy (users don't give away their emails or other contact details) users opt-in with more desire than for traditional emails lists.

  They also have ability to unsubscribe from receiving notification anytime they want. Studies show that the **churn rate** for subscribers of web push notifications during the first year is **less than 10%**.

* ##### Instant delivery

  The moment you click "Send", your message will be delivered to the users in amount of second. Notimatica is highly scalable service specifically designed to serve millions of notifications per minute.

* ##### Delivery with guaranty

  Unlike emails which can be filtered as a spam, web push notifications are always delivered to the subscriber.

* ##### High conversion rate (CTR)

  Our studies show that compared with traditional email marketing which has average 10-20% conversion rate, web push notifications have staggering **60-80% conversion rate**.

* ##### No need to build a mobile app

  You can get all the benefits of mobile push technology with web push notifications. They work alike. No need to invest your limited resources in building mobile app just to get ability to notify users.

{#how-to-get-started}
## How to get started?

Follow our Configuration guide to setup a new project in Notimatica.
Follow our Installation guide 

  1. Start with step-by-step [Getting Prerequistes Guide](/docs/prerequisites).
  1. Next stop is [Project Setup Guide](/docs/project-setup) to configure your project in Notimatica.
  1. At last follow [SDK Installation Guide](/docs/sdk-installation) to put our lightweight JavaScript SDK on your website.

  You may also be interested in:
* [JavaScript SDK](/docs/sdk-api) API reference.
* [Server REST API](https://notimatica.api-docs.io) for custom server-to-server integrations.
* Ready-to-use modules for CMS ([WordPress](/docs/wordpress), [Drupal](/docs/drupal), [Joomla](/docs/joomla) and others)

If you have questions, comments or you can't find something, please visit [Troubleshooting](/docs/troubleshooting), [Examples](/docs/examples) or drop us a line at ([support@notimatica.io](mailto:support@notimatica.com).
