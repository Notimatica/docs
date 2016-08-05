# Prerequisites

Before start, you have to make some preparations in order to provide Notimatica with prerequisites for Web Push Notifications delivery. Don’t be afraid this guide will help you.

{.toc}
1. [Google Chrome support (GCM)](#google-chrome-support)
1. [Apple Safari support (optional)](#apple-safari-support)
    1. [Developer license](#developer-license)
    1. [Website Push ID Certificate](#website-push-id-certificate)

{#google-chrome-support}
## Google Chrome Support (GCM)

To support Google Chrome you need to create an app in Google Services, obtain **Google Server API Key** and **Google Project Number**.

{.step-text}
* ##### Go to [Google Services Wizard](https://developers.google.com/mobile/add?platform=android&cntapi=gcm)

* ##### Choose App name and Android package name

  Type any new App name (better be your site name) or select an existing app from the dropdown. We don't need the Android package name, but you have to type something here to continue like `test.test` as shown on the screen below. Finally, click "Choose and configure services".

  ![Google Services Wizard](/static/google1.png "Google Services Wizard - Step 1"){.img-rounded .img-shadow .img-responsive .center-block}

  Wait a bit for the project to be created.

* ##### Click "Enable Google Cloud Messaging"

  ![Google Services Wizard](/static/google2.png "Google Services Wizard - Step 2"){.img-rounded .img-shadow .img-responsive .center-block}

* ##### Save the two values listed

  You'll need Server API Key and Sender ID (also known as the Project Number) a bit later.

  ![Google Services Wizard](/static/google3.png "Google Services Wizard - Step 3"){.img-rounded .img-shadow .img-responsive .center-block}

Congratulations, now you are ready for Google Chrome support.

The next step is to install our **JavaScript SDK** on your website – [SDK Installation guide](/docs/installation).

{#apple-safari-support}
## Safari support (optional)

{#developer-license}

<div class="callout callout-warning" role="alert">

#### Developer License

To complete this guide you need to have an iOS or Mac OS developer account on the [Developer Programs](https://developer.apple.com/programs/) page.

</div>


{#website-push-id-certificate}
### [Website Рush ID Сertificate](#website-push-id-certificate){name="website-push-id-certificate"}

{.step-text}
* ##### Go to [Website Push IDs section](https://developer.apple.com/account/ios/identifier/websitePushId/landing) on Apple Member Center.

  ![Apple Member Center](/static/apple2.png "Apple Member Center - Step 1"){.img-rounded .img-shadow .img-responsive .center-block}

* ##### Create a unique Website Push ID.

  **Website Push ID Description**. This is the name used throughout the Provisioning Portal to refer to your website. Use it to label your Website Push IDs into a more human-readable format for your own benefit.

  **Identifier**. Type a reverse-domain name of your website, such as web.com.your-domain. An Identifier should start ‘web.’ prefix.

  ![Apple Member Center](/static/apple3.png "Apple Member Center - Step 2"){.img-rounded .img-shadow .img-responsive .center-block}

* ##### Go to [Certificates section](https://developer.apple.com/account/ios/certificate/)

  ![Apple Member Center](/static/apple4.png "Apple Member Center - Step 3"){.img-rounded .img-shadow .img-responsive .center-block}

* ##### Add a new Certificate

  ![Apple Member Center](/static/apple5.png "Apple Member Center - Step 4"){.img-rounded .img-shadow .img-responsive .center-block}

  Choose ‘Website Push ID Certificate’ option.

  ![Apple Member Center](/static/apple6.png "Apple Member Center - Step 5"){.img-rounded .img-shadow .img-responsive .center-block}

* ##### Choose application

  During certificate creation process choose the **Website Push ID** which was created a minute ago and follow the steps in the wizard.

  ![Apple Member Center](/static/apple7.png "Apple Member Center - Step 6"){.img-rounded .img-shadow .img-responsive .center-block}

* ##### Download the Website Рush ID Сertificate.

  ![Apple Member Center](/static/apple8.png "Apple Member Center - Step 7"){.img-rounded .img-shadow .img-responsive .center-block}

  We need a private key file (.p12) to configure Safari in Notimamica. Launch Keychain Access Application and select the ‘Keys’.

* ##### Click on the private key associated with your Website Push ID Certificate.

  ![Apple Member Center](/static/apple9.png "Apple Member Center - Step 8"){.img-responsive .center-block}

* ##### In context-menu click ‘Export’.

* ##### Choose the directory to save the Private Key file (.p12).

  ![Apple Member Center](/static/apple10.png "Apple Member Center - Step 9"){.img-responsive .center-block}

* ##### You will be asked to create a password. You can leave both fields blank.

  ![Apple Member Center](/static/apple11.png "Apple Member Center - Step 10"){.img-responsive .center-block}


Congratulations, you've successfully configured prerequisites for Apple Safari.

The next step is to install our JavaScript SDK on your website – [SDK Installation guide](/docs/installation).
