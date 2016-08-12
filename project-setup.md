# Project Setup

Secondly, you have to create a new Project in Notimatica. Let's do it together step by step.

<div class="callout callout-info" role="alert">

#### HTTP & HTTPS Support

Notimatica supports both HTTPS and HTTP websites, yet browsers require only HTTPS. We workaround this by sending push notifications to HTTP websites from `your-subdomain.notimatica.io` which is an HTTPS domain. The shortcoming is that it requires HTTP websites to show an additional popup window to opt-in users.

</div>

<div class="callout callout-warning" role="alert">

#### Prerequisites

If you don’t have **Google Server API Key** and **Google Project Number** then go to [Prerequisites Guide](/docs/prerequisites)  first.

</div>

{.toc}
1. [Create New Project](#create-new-project)
1. [Configure Chrome and Firefox](#configure-chrome-and-firefox)
1. [Configure Safari (optional)](#configure-safari)
1. [Include and initialize SDK](#include-and-initialize-sdk)

{#create-new-project}
## Create New Project

1. Go to [Notimatica's Dashboard](https://my.notimatica.io) and click "New project".
1. Enter the **Name** and **URL** of your websute. Note that URL should contain prefix (`http://` or `https://`).
1. Type **Subdomain**. Usually it may be the same as the Name of your website.
1. Upload **Project icon**. The icon should be squared 192x192 PNG image.
1. Click on "Create". Wait for project to be created.
1. Congratulation, you have created first project in Notimatica.

{#configure-chrome-and-firefox}
## Configure Chrome and Firefox

1. Go to **Project → Settings → Google Chrome, Mozilla Firefox** and click "Connect".
1. In the popup window type your **Google Server API Key** (API key) and **Google Project Number** (Sender ID) ([where can I get these?](/docs/prerequisites#google-chrome-support)) and click "Connect".
{#configure-chrome-and-firefox-download-sdk}
1. Download and unzip the SDK files by "Download package" link that has appeared. Inside package you should have:
    * `manifest.json`
    * `notimatica-sw.js`
1. Upload these files to the root directory of your website.
1. All set! Now go to [SDK Installation Guide](/docs/sdk-installation) to complete the last step.

{#configure-safari}
## Configure Safari

<div class="callout callout-info" role="alert">

#### Safari Support Is Optional
* Using Google Chrome and Mozilla Firefox as your only web push notification platform is totally fine as they have 80% market share combined.
* iOS and Windows are currently not supported

</div>

1. Go to **Project → Settings → Apple Safari** and click "Connect".
1. Upload a Private Key file `.p12` ([where can I get this?](/docs/prerequisites#apple-safari-support)) and click "Connect".
1. If you have already downloaded and unziped the SDK files by "Download package" link for Google Chrome support, then go  straight to [SDK Installation Guide](/docs/sdk-installation) to complete the last step. 

