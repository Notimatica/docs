# Prerequisites

First of all, you have to obtain prerequisites from Google and Apple (optionaly), which are neccesary to setup you Project in Notimatica. 

{.toc}
1. [Google Chrome Support (GCM)](#google-chrome-support)
1. [Apple Safari Support (APN)](#apple-safari-support)

{#google-chrome-support}
## Google Chrome Support (GCM)

To support Google Chrome you need to create an app in Google Services, obtain **Google Server API Key** and **Google Project Number**.

{.step-text}

* ##### Go to Google Services Wizard

  Go to – [https://developers.google.com/mobile/add?platform=android&cntapi=gcm](https://developers.google.com/mobile/add?platform=android&cntapi=gcm)

* ##### Choose App name and Android package name

  Type new **App name** (it can be the name of your website) or select an existing app from the dropdown. 
  We don't need the Android package name, but you have to type something here to continue like `test.test` as shown on the screen below. Finally, click "Choose and configure services".

  ![Google Chrome Support](/static/prerequisites/google1.png "Google Chrome Support - Step 1"){.img-rounded .img-shadow .img-responsive .center-block}

  Please, wait for the project to be created.

* ##### Click "Enable Google Cloud Messaging"

  ![Google Chrome Support](/static/prerequisites/google2.png "Google Chrome Support - Step 2"){.img-rounded .img-shadow .img-responsive .center-block}

* ##### Save the two values 

  You'll need **Server API Key** and **Sender ID** (also known as the Project Number) a bit later in Project Setup Guide.

  ![Google Chrome Support](/static/prerequisites/google3.png "Google Chrome Support - Step 3"){.img-rounded .img-shadow .img-responsive .center-block}

* ##### Congratulations
  Now you're ready to enable Google Chrome Support in Notimatica.

  The next step is to install **JavaScript SDK** on your website with the help of [SDK Installation Guide](/docs/installation).

{#apple-safari-support}

## Apple Safari Support (APNS)

<div class="callout callout-info" role="alert">

#### Safari Support is Optional
* Using Google Chrome and Mozilla Firefox as your only web push notification platform is totally fine as they have 80% market share combined.
* iOS and Windows are currently not supported

</div>

{#apple-developer-license}
<div class="callout callout-warning" role="alert">

#### Apple Developer License

* To complete this guide you need to have an active iOS or Mac OS developer account in the [Apple Developer Program](https://developer.apple.com/programs/).

</div>

{#website-push-id-certificate}
{.step-text}

* ##### Go to Website Push IDs section of Provisioning Portal.
  Go to – [https://developer.apple.com/account/ios/identifier/websitePushId/landing](https://developer.apple.com/account/ios/identifier/websitePushId/landing)

  ![Apple Safari Support](/static/prerequisites/apple2.png "Apple Safari Support - Step 1"){.img-rounded .img-shadow .img-responsive .center-block}

* ##### Create new Website Push ID

  Type new **Website Push ID Description** (it can be the name of your website). Next, type **Identifier** as a reverse-domain name of your website, such as web.com.your-domain (it should start with `web.` prefix). Finally, click "Continue".

  ![Apple Safari Support](/static/prerequisites/apple3.png "Apple Safari Support - Step 1"){.img-rounded .img-shadow .img-responsive .center-block}

  Click "Register"

  ![Apple Safari Support](/static/prerequisites/apple4.png "Apple Safari Support - Step 2"){.img-rounded .img-shadow .img-responsive .center-block}

* ##### Go to Certificates section on Provisioning Portal.
  Go to – [https://developer.apple.com/account/ios/certificate/](https://developer.apple.com/account/ios/certificate/)

  ![Apple Safari Support](/static/prerequisites/apple5.png "Apple Safari Support - Step 3"){.img-rounded .img-shadow .img-responsive .center-block}

* ##### Create new Certificate

  Choose ‘Website Push ID Certificate’ option.

  ![Apple Safari Support](/static/prerequisites/apple6.png "Apple Safari Support - Step 4"){.img-rounded .img-shadow .img-responsive .center-block}

* ##### Select Website Рush ID

  Сhoose the **Website Push ID** which we created a moment ago and click "Continue".

  ![Apple Safari Support](/static/prerequisites/apple7.png "Apple Safari Support - Step 5"){.img-rounded .img-shadow .img-responsive .center-block}

* ##### Download the Website Рush ID Сertificate

  ![Apple Safari Support](/static/prerequisites/apple8.png "Apple Safari Support - Step 6"){.img-rounded .img-shadow .img-responsive .center-block}

* ##### Launch Keychain Access app

  ![Apple Safari Support](/static/prerequisites/apple13.png "Apple Safari Support - Step 7"){.center-block}
 
* ##### Add Certificate file to Keychain Access.
  Make sure you've placed it into the "Login" keychain under "Certificates" category.

* ##### Export the Private Key file
  In context menu of newly added certificate click "Export".

  ![Apple Safari Support](/static/prerequisites/apple12.png "Apple Safari Support - Step 9"){.img-responsive .center-block}

* ##### Choose the directory to save Private Key file

  ![Apple Safari Support](/static/prerequisites/apple10.png "Apple Safari Support - Step 10"){.img-responsive .center-block}

* ##### Set Private Key password
  You'll be asked to create a password. Please, leave both fields blank.

  ![Apple Safari Support](/static/prerequisites/apple11.png "Apple Member Center - Step 11"){.img-responsive .center-block}

* ##### Hurray!
  It wasn't easy, but you've nailed it! Now you have prerequisites for Apple Safari Support in Notimatica.

  The next step is to install **JavaScript SDK** on your website with the help of [SDK Installation Guide](/docs/installation).