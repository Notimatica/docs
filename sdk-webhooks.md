# JavaScript SDK Webhooks

{.toc}
* [Overview](#overview)
* [Available Events](#events)

{#overview}
## Overview

Webhooks are "user-defined HTTP callbacks". They are maintained by third-party users and can be triggered by SDK events.

You can specify your own url to trigger on events in `webhooks` options like this:

```javascript
var Notimatica = Notimatica || [];
Notimatica.push(['init', {
  project: 'PROJECT_ID',
  subdomain: 'SUBDOMAIN',
  webhooks: {
    'event': 'http://webhook-url'
  }
}]);
```

When event is triggered, SDK will send a POST request with all info about the received notification in JSON format.

{#overview}
## CORS

Webhook requests will be done by browser and in most cases will be sent from other domain. That's why you may want to set [CORS](https://en.wikipedia.org/wiki/Cross-origin_resource_sharing) headers on your backend.

If it has CORS, additional headers will be sent. If you want this and 100% sure that you server support CORS headers, enable it by setting `webhooksCors` option to `true`. By default it is `false`.

{#events}
## [Available Events](#events){name="events"}

{.table .table-bordered .table-striped .table-info}
| Event | Description |
|-------|-------------|
| `notification:close` | Will be triggered when user closes the message by clicking the close button or swipes it |
| `notification:click` | Will be triggered when user clicks on the message |
| `notification:show` | Will be triggered when message was received and showed to the user |
