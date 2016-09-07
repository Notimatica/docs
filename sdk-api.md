# JavaScript SDK API

Since SDK is loaded async way, all it's methods should be called via `push([METHOD_NAME, ARGS...])` wrapper. The only exception is when you are 100% sure that it is already loaded and inited. For instance, in events callbacks.

Example:

```javascript
// Subscribe to notifications
Notimatica.push(['subscribe']);
```

{.toc}
* [init({Object} options)](#init)
* [subscribe()](#subscribe)
* [unsubscribe()](#unsubscribe)
* [isSubscribed() : {Boolean}](#isSubscribed)
* [isUnsubscribed() : {Boolean}](#isUnsubscribed)
* [on({String} event, {Function} callback)](#on)
* [emit({String} event)](#emit)
* [resetHistory](#resetHistory)
* [resetState](#resetState)
* [resetSDK](#resetSDK)

{#init}
## init({Object} options)

Initialize SDK. Should be called on every page of your site.

<div class="callout callout-info" role="alert">

#### Note!

This method should be called once. Multiple calls won't cause any additional effect but will show a warning in the browser console.

</div>

**Params**
  * `{Object} options` - Map of options

**Example**

```javascript
Notimatica.push(['init', {
  project: 'PROJECT_ID',
  subdomain: 'SUBDOMAIN'
}]);
```

{#subscribe}
## subscribe()

Start subscription process.

**Example**

```javascript
Notimatica.push(['subscribe']);
```

{#unsubscribe}
## unsubscribe()

Unsubscribes user from notifications

**Example**

```javascript
Notimatica.push(['unsubscribe']);
  ```

{#isSubscribed}
## isSubscribed() : {Boolean}

If user is subscribed.

**Returns**
  * `{Boolean}` - `true` if user is subscribed, `false` if not

**Example**

```javascript
if (Notimatica.push(['isSubscribed'])) {
  alert('You are subscribed')
};
```

{#isUnsubscribed}
## isUnsubscribed() : {Boolean}

If user is or was unsubscribed.

**Returns**
  * `{Boolean}` - `true` if user is not subscribed, `false` if is    

**Example**

```javascript
if (Notimatica.push(['isSubscribed'])) {
  alert('You are not subscribed')
};
```

{#on}
## on({String} event, {Function} callback)

Subscribe to SDK event.

**Params**
  * `{String} event` - Event name
  * `{Function} callback` - The callback to fire when event is emitted

**Example**

```javascript
Notimatica.push(['on', 'ready', function () {
  alert('Notimatica SDK is ready')
}])
```

{#emit}
## emit({String} event)

Trigger the event.

**Params**
  * `{String} event` - Event name

**Example**

```javascript
Notimatica.push(['emit', 'error', 'Something bad happened'])
```

{#resetHistory}
## resetHistory()

Reset history of received notifications.

**Example**

```javascript
Notimatica.push(['resetHistory'])
```

{#resetState}
## resetState()

Reset saved state and settings.

**Example**

```javascript
Notimatica.push(['resetState'])
```

{#resetSDK}
## resetSDK()

Reset already inited SDK.

**Example**

```javascript
Notimatica.push(['resetSDK'])
```
