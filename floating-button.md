# Floating Button

Simple way to provide user action button to subscribe to notifications. With nice popover to interact with user that can be automatically shown if `autoSubscribe` is [enabled](/docs/examples).

![floating button](/static/floating-button.png "Floating button"){height="200"}

{.toc}
* [Installation](#installation)
* [Message](#message)
* [Options](#options)
* [Strings](#strings)

{#installation}
## Installation

```javascript
var Notimatica = Notimatica || [];
Notimatica.push(['init', {
  project: 'PROJECT_ID',
  plugins: {
    button: {
      enable: true,
      position: 'bottom-left'
    }
  }
}]);
```

{#message}
## Message

Moreover, you can send a message to the user and it will appear as a nice bubble on the button and will be shown in the prompt after user clicks on it.

You can do it by triggering `user:message` [event](/docs/sdk-events) like this:

```javascript
Notimatica.push([
  'emit',
  'user:message',
  'You have a message!',
  'Something on our site needs you attention.'
])
```

**Where params are:**
  1. method [`emit`](/docs/sdk-api#emit) tells SDK that we want to trigger an [event](/docs/sdk-events)
  1. the event name
  1. title of the message (if you set it to `null`, it won't be shown)
  1. text of the message

![new message](/static/new-message.png "New message"){height="100"}
![show message](/static/show-message.png "Show message"){height="100"}


{#options}
## Options

{.table .table-bordered .table-striped}
| Name | Type | Default value | Description |
|------|------|---------------|-------------|
| autorun | Boolean | `true` | Run plugin right after it loaded. Adds ability to run it manually |
| target | String | `'body'` | Selector of the element that will be appended with plugin's html |
| css | String | `Notimatica.options.sdkPath + '/notimatica-button.css'` | Where to get css |
| cssTarget | String | `'head'` | Selector of the element that will be appended with plugin's css styles |
| position | String | `'bottom-right'` | Position of the button on the screen. Can be: bottom-right, bottom-left, top-right or top-left |
| usePopover | Boolean | true | Show popover with subscription message on button click, or start subscribing |

Also you can provide onclick callback that will be triggered on Subscribe/Unsubscribe button on popover or on button itself. It can be done via `click` option. Default is pretty simple:

```javascript
function {
  Notimatica.isSubscribed()
    ? Notimatica.unsubscribe()
    : Notimatica.subscribe()
}
```

{#strings}
## Strings

{.table .table-bordered .table-striped .table-info}
| String | Default |
|--------|---------|
| `popover.subscribe` | Do you want to receive desktop notifications from our site? Click Subscribe button! |
| `popover.unsubscribe` | If you don't want to receive notifications anymore, click Unsubscribe button. |
| `popover.button.subscribe` | Subscribe |
| `popover.button.unsubscribe` | Unsubscribe |
| `tooltip.subscribe` | Subscribe to notifications |
| `tooltip.unsubscribe` | Unsubscribe from notifications |
| `tooltip.message` | There is a message for you |
