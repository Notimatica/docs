# Prerequisites

Before we start, you have to make some preparations in order to provide us with info used in notifications send process. Don’t be afraid this guide will help you.

{.toc}
1. [Google Chrome support (GCM)](#google-chrome-support)
1. [Apple Safari support (optional)](#apple-safari-support)
    1. [Developer license](#developer-license)
    1. [Website Push ID Certificate](#website-push-id-certificate)

{#google-chrome-support}
## [Google Chrome support (GCM)](#google-chrome-support){name="google-chrome-support"}

To support Google Chrome you need to create an app in Google Services, obtain **Google Server API Key** and **Google Project Number**.

{.step-text}
* ##### Go to [Google Services Wizard](https://developers.google.com/mobile/add?platform=android&cntapi=gcm)

  скрин

* ##### Choose your application name

  Or select an existing app from the dropdown.

  скрин

* ##### Enter package name

  We do not need the Android package name, but you have to type something here to continue. Please type test.test as shown on the screen.

  скрин

* ##### Click on "Choose and configure services"

  Wait a bit for the project to be created.

  скрин

* ##### Click от "Enable Google Cloud Messaging"

  скрин

* ##### Save the two values listed

  You'll need Server API Key and Sender ID (also known as the Project Number) a bit later.

Congratulations, you are ready for Google Chrome support.

The next step is to install our **JavaScript SDK** on your website – [SDK Installation guide](/docs/installation).

{#apple-safari-support}
## [Safari support (optional)](#apple-safari-support){name="apple-safari-support"}

{#developer-license}
### [Developer License](#developer-license){name="developer-license"}

To complete this guide you need to have an iOS or Mac OS developer account on the developer programs page. ([https://developer.apple.com/programs/](https://developer.apple.com/programs/))

{#website-push-id-certificate}
### [Website Рush ID Сertificate](#website-push-id-certificate){name="website-push-id-certificate"}

{.step-text}
* ##### Go to Website push IDs section on Apple Member Center
  ([https://developer.apple.com/account/ios/identifier/websitePushId/landing](https://developer.apple.com/account/ios/identifier/websitePushId/landing)) of the Certificates, Identifiers & Profiles section in Member Center.

* ##### Create a unique Website Push ID.

  **Identifier**. Type a reverse-domain name of your website, such as web.com.your-domain. An Identifier should start ‘web.’ prefix.

  **Website Push ID Description**. This is the name used throughout the Provisioning Portal to refer to your website. Use it to label your Website Push IDs into a more human-readable format for your own benefit.

* ##### Go to Certificates section

  ([https://developer.apple.com/account/ios/certificate/](https://developer.apple.com/account/ios/certificate/))

* ##### Add a new Certificate

  Choose ‘Website Push ID Certificate’ option.

* ##### Choose application

  During certificate creation process choose the **Website Push ID** which was created a minute ago and follow the steps in the wizard.

* ##### Download the Website Рush ID Сertificate.

  We need a private key file (.p12) to configure Safari in Notimamica. Launch Keychain Access Application and select the ‘Keys’.

* ##### Click on the private key associated with your Website Push ID Certificate.

* ##### In context-menu click ‘Export’.

* ##### You will be asked to create a password. You can leave both fields blank.

* ##### Save the Private Key file (.p12).

Congratulations, you've successfully configured prerequisites for Apple Safari.

The next step is to install our JavaScript SDK on your website – [SDK Installation guide](/docs/installation).
