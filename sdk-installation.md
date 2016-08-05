# JavaScript SDK Installation

The last thing to make everything work is to include our JavaScript SDK on your website.

{.toc}
* [Include manifest file](#include-manifest-file)
* [Include JavaScript SDK file](#include-sdk-file)
* [Initialize SDK](#initialize-sdk)
* [Full Example](#full-example)
* [Testing in sandbox](#testing-in-sandbox)

{#include-manifest-file}
## Include manifest file

Include **manifest.json** at the top of your `<head>` tag.

* An error occurs if **manifest.json** is included in `<body>`.
* Your `<link rel="manifest" href="/manifest.json">` must appear before any other `<link rel="manifest" ...>` in `<head>`, otherwise it will not be found.

{#include-sdk-file}
## Include JavaScript SDK file

Include `<script src="https://cdn.notimatica.io/sdks/latest/notimatica-sdk.js" async></script>` in your `<head>` tag.

Our SDK is fully asynchronous and event based so you don't have to worry that you place it in the head, it will not slow your page loading.

{#initialize-sdk}
## Initialize SDK

When SDK file is included, it provides an easy to use API. All available methods are described in the [Javascript SDK](/docs/javascript-sdk) section. But first, lets initialize it.

First, you have to find your Project ID. It is a unique string like `08823592-135f-5576-9a91-f3a0675aa1d1` that can be found  in **All Projects → Project ID** or **Project Settings → Edit Project → Project ID**.

Then you need to place a small peace of JavaScript code right below SDK file.

{.line-numbers}
```javascript
var Notimatica = Notimatica || [];
Notimatica.push(['init', {
  project: 'PROJECT_ID'
}]);
```

> Don't forget to replace `PROJECT_ID` with Project ID you obtained earlier.

<!--This is a minimum setup that is needed to make everything work. When your customer will visit your site, he will see automatic prompt to subscribe to notifications. But this way is not user friendly.

Luckily our SDK is flexible enough to give you an easy way to modify or customize default behavior. You can do it by setting additional options in init method like this:

{.line-numbers}
```javascript
var Notimatica = Notimatica || [];
Notimatica.push(['init', {
  project: 'PROJECT_ID',
  autorun: false
}]);
```

In this example we set autorun to false, so we say that we don't want SDK prompt users to subscribe automatically, we want to do it manually. -->

<div class="callout callout-info" role="alert">

All additional information about extra options with lots of examples you can find in [JavaScript SDK](/docs/javascript-sdk) section.

</div>

{#full-example}
## Full Example

{.line-numbers}
```markup
<head>
<link rel="manifest" href="/manifest.json">
<script src="https://cdn.notimatica.io/sdks/latest/notimatica-sdk.js" async></script>
<script>
  var Notimatica = Notimatica || [];
  Notimatica.push(['init', {
    project: '08823592-135f-5576-9a91-f3a0675aa1d1',
    autorun: false,
    plugins: {
      button: {
        enable: true
      }
    }
  }]);
</script>
</head>
```

In this example we:

1. Include **manifest.json**
1. Include JavaScript SDK file
1. Init SDK
    1. Set project ID
    1. Disable autorun
    1. Enable [Floating button plugin](/docs/button-plugin) for easy and verbose subscription process


<div class="callout callout-info" role="alert">

#### Testing in sandbox

When testing your project in sandbox (https://localhost), it may be helpful to run browser with additional flags to bypass a warning of invalid certificate. Here are tips:

* **Chrome**: Run Chrome with `--ignore-certificate-errors` flag.
* **Firefox and Safari**: Both have mechanisms to create exceptions for specific certificates.

</div>
