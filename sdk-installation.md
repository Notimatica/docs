# JavaScript SDK Installation

Finally, to make things work you have to include our JavaScript SDK on your website.

{.toc}
* [Include manifest file](#include-manifest-file)
* [Include JavaScript SDK file](#include-sdk-file)
* [Initialize SDK](#initialize-sdk)

{#include-manifest-file}
## Include manifest file

Include `manifest.json` at the top of your `<head>` tag.

<div class="callout callout-warning" role="alert">

#### Please Note
* An error occurs if `manifest.json` is included in `<body>`.
* Your `<link rel="manifest" href="/manifest.json">` must appear before any other `<link rel="manifest" ...>` in `<head>`, otherwise it will not be found.

</div>

{#include-sdk-file}
## Include JavaScript SDK file

Include `<script src="https://cdn.notimatica.io/sdks/latest/notimatica-sdk.js" async></script>` in your `<head>` tag.

Dont' worry our JavaScript SDK is fully asynchronous and event-based so it won't affect page loading.

{#initialize-sdk}
## Initialize SDK

Place a small peace of JavaScript code right below SDK call.

{.line-numbers}
```javascript
var Notimatica = Notimatica || [];
Notimatica.push(['init', {
  project: 'PROJECT_ID',
  subdomain: 'SUBDOMAIN',
  safariWebId: 'web.com.mydomain'
}]);
```

You can find your Project ID and Subdomain in **Dashboard → Projects** ([take me there](https://my.notimatica.io/projects)).
In case I've added Apple Safari support you need to add safariWebId parameter with your Apple Web Push ID.

Now let's see a real life working example:

{.line-numbers}
```markup
<head>
<link rel="manifest" href="/manifest.json">
<script src="https://cdn.notimatica.io/sdks/latest/notimatica-sdk.js" async></script>
<script>
  var Notimatica = Notimatica || [];
  Notimatica.push(['init', {
    project: '08823592-135f-5576-9a91-f3a0675aa1d1',
    subdomain: 'testdomain',
    debug: true,
    plugins: {
      button: {
        enable: true,
        autorun: true,
        position: 'bottom-right'
      }
    }
  }]);
</script>
</head>
```

In this example we:

1. Include `manifest.json`
1. Include JavaScript SDK file
1. Initialize SDK
    1. Set Project ID
    1. Set Subdomain
    1. Enable debug-mode to see error messages in Developer Tools Console.
    1. Enable [Floating button plugin](/docs/button-plugin) in the bottom right corner. For additional ease of web push opt-in process we've enabled autorun option.

<div class="callout callout-info" role="alert">

#### Want More?

Checkout more [Examples & Tutorials](/docs/examples) as well as comprehensive documentation on [JavaScript SDK](/docs/javascript-sdk) with complete list of options.

</div>

<div class="callout callout-info" role="alert">

#### Testing In Sandbox

When testing your project in sandbox (`https://localhost`), it may be helpful to run browser with additional flags to bypass a warning of invalid certificate. Here are tips:

* **Chrome**: Run Chrome with `--ignore-certificate-errors` flag.
* **Firefox and Safari**: Both have built-in mechanisms to create exceptions for specific certificates.

</div>
