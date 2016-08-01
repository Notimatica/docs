# Setup

<div class="callout callout-info" role="alert">

#### HTTP & HTTPS support

Notimatica supports both HTTPS and HTTP websites. In case you HTTPS there is now problem for you, but with HTTP there is an issue. Generally speaking web push notifications do not support HTTP at all, but we work around this by sending notifications from a subdomain of notimatica.io, which is HTTPS website. It means that notifications are coming from your-subdomain.notimatica.io. Due to browser restrictions, this workaround requires a popup window to be shown for users to subscribe.

</div>

<div class="callout callout-warning" role="alert">

#### Google application

If you don’t have Google Server API Key and Google Project Number then complete the [Prerequisites](/docs/prerequisites) guide first.

</div>

{.toc}
1. [Create New Project](#create-new-project)
1. [Configure Chrome and Firefox](#configure-chrome-and-firefox)
1. [Configure Safari (optional)](#configure-safari)
1. [Include and initialize SDK](#include-and-initialize-sdk)

{#create-new-project}
## [Create New Project](#create-new-project){name="create-new-project"}

1. Go to our Dashboard and click "New project".
1. Enter the *Name* and *URL*. The *URL* should begin with prefix (http:// or https://) and not include subfolders.
1. Enter *Subdomain*. The *Subdomain* is necessary for HTTP websites.
1. Upload *Project icon*. The icon should be square .png image 192x192px.
1. Click on "Create" button. Wait for project to be created.

{#configure-chrome-and-firefox}
## [Configure Chrome and Firefox](#configure-chrome-and-firefox)

1. In a newly created project go to **Project’s settings → Google Chrome, Mozilla Firefox** and click "Connect".
1. Enter your Google Server API Key and Google Project Number (where can I get these?) and click "Connect".
1. Download and unzip the SDK files by "Download package" link. You should have:
    * manifest.json
    * notimatica-sw.js
1. Upload the files to the root of your site directory.

{#configure-safari}
## [Configure Safari (optional)](#configure-safari)

<div class="callout callout-info" role="alert">

#### Please note

* iOS and Windows currently are **not supported**
* Using Google Chrome and Mozilla Firefox as your only web push platform is totally fine as they have 80% market share combined.

</div>

1. In a newly created project go to **Project’s settings → Apple Safari** and click "Connect".
1. Upload a Private Key file (.p12) you obtained in prerequisites step and click "Connect".

That's it. You are at the finish line and only one [step](/docs/installation) ahead
