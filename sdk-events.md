# JavaScript SDK Events

SDK emits events for every major...events :smile: so you can easily subscribe on them and provide your own callbacks.

{.toc}
* [Subscribing](#subscribing)
* [Public Events](#public-events)
* [Internal Events](#internal-events)

{#subscribing}
## Subscribing

It is extremely easy to subscribe to SDK events:

```javascript
Notimatica.push(['on', 'subscribe:success', function () {
  alert('From now you are subscribed to notifications!')
}])
```

First argument is method `on()`, second is an event name, third is a callback.

{#public-events}
## Public Events

{.table .table-bordered .table-striped}
| Event | Vars | Description |
|-------|------|-------------|
| `ready` | - | Notimatica SDK is fully loaded and ready for action |
| `unsupported` | <samp>{String} message</samp> | User's browser doesn't support notifications |
| `warning` | <samp>{String} message</samp> | Warning was emitted |
| `error` | <samp>{*} err</samp> | Error was emitted |
| `subscribe:start` | - | User started subscription |
| `subscribe:success` | <samp>{String} user's Notimatica internal uuid</samp> | User successfully subscribed |
| `subscribe:fail` | <samp>{*} err</samp> | Something failed subscription process |
| `unsubscribe:start` | - | User started unsubscribing |
| `unsubscribe:success` | - | User successfully unsubscribed |
| `unsubscribe:fail` | <samp>{*} err</samp> | For some reason user failed to unsubscribe |

{#internal-events}
## Internal Events

{.table .table-bordered .table-striped}
| Event | Vars | Description |
|-------|------|-------------|
| `driver:ready` | <samp>{Object} driver</samp> | Push notifications driver inited and ready |
| `plugin:ready` | <samp>{Object} plugin</samp> | Plugin was loaded and ready to init |
| `autorun:disable` | - | If SDK should disable autorun forever |
| `iframe:ready` | - | If HTTP fallback iframe is loaded |
| `subscribe:subscription` | <samp>{String} browser's endpoint</samp> | Driver received browser's endpoint |
| `register:start` | <samp>{Object} user's data</samp> | SDK makes attempt to register user in Notimatica |
| `register:success` | <samp>{Object} Notimatica user</samp> | Registration succeeded |
| `register:fail` | <samp>{*} err</samp> | Registration failed |
| `unregister:start` | - | SDK makes attempt to unregister from Notimatica |
| `unregister:success` | - | Notimatica forgot about user |
| `unregister:fail` | <samp>{*} err</samp> | Notimatica failed to unregister user |

<div class="callout callout-info" role="alert">

#### Note!

If debug mode is on, SDK will send logs into console for every event emitted.

</div>
