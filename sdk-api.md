# JavaScript SDK API

Since SDK is loaded async way, all it's methods should be called via `push([METHOD_NAME, ARGS...])` wrapper. The only exception is when you are 100% sure that it is already loaded and inited. For instance, in events callbacks.

- `init({Object} options)` - Init SDK
- `subscribe()` - Subscribe to notifications
- `unsubscribe()` - Unsubscribe from notifications
- `isSubscribed() : {Boolean}` - If user us subscribed
- `isUnsubscribed() : {Boolean}` - If user is unsubscribed

Example:

```javascript
// Subscribe to notifications
Notimatica.push(['subscribe']);
```
