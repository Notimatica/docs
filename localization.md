# Localization

Every string in SDK can be localized, even text of the HTTP fallback popup, so you can handle multiple languages.

{.toc}
* [Mechanism](#mechanism)
* [Popup](#popup)

{#mechanism}
## Mechanism

All strings have a unique namespaced ID and can be translated on any language you like.

By default all strings are for `en` language. If you want to overwrite any of them or add your own language, add them to `strings` options like this:

```javascript
var Notimatica = Notimatica || [];
Notimatica.push(['init', {
  project: 'PROJECT_ID',
  subdomain: 'SUBDOMAIN',
  strings: {
    ru: {
      'tooltip.subscribe': 'Подписаться на новости',
    }
  }
}]);
```

Here we translated `tooltip.subscribe` string to Russian, so that if your page will visit russian-speaking customer, he will see Russian translation.

All strings for tooltip are namespaced with `tooltip` prefix.

{#popup}
## Popup

HTTP fallback popup can be translated too.

{.table .table-bordered .table-striped .table-info}
| String | Default |
|--------|---------|
| `popup.welcome` | Subscribe to {project} |
| `popup.subscribe` | Do you want to receive notifications from {project}? |
| `popup.subscribed` | You are subscribed to notifications from {project}. |
| `popup.unsupported` | Your browser don't support push notifications. |
| `popup.buttons.subscribe` | Subscribe |
| `popup.buttons.unsubscribe` | Unsubscribe |
| `popup.buttons.cancel` | Cancel |

As you can notice some strings contain `{project}` placeholder. It is a place where project's name will be placed.
