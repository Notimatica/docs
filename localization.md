# Localization

Every string in SDK can be localized, even text of the HTTP fallback popup, so you can handle multiple languages.

{.toc}
* [Strings Translation](#strings-translation)
* [Locale Detection](#locale-detection)
* [Popup](#popup)

{#strings-translation}
## String Translation

All strings have a unique ID and can be translated on any language you like.

By default all strings are for `en` and `ru` languages. If you want to overwrite any of them or add your own language, add them to `strings` options like this:

```javascript
var Notimatica = Notimatica || [];
Notimatica.push(['init', {
  project: 'PROJECT_ID',
  subdomain: 'SUBDOMAIN',
  strings: {
    es: {
      'tooltip.subscribe': 'Suscribirse a las noticias',
    }
  }
}]);
```

Here we translated `tooltip.subscribe` string to Spanish, so that if your page will visit spanish-speaking customer, he will see Spanish translation.

{#locale-detection}
## Locale Detection

By default SDK tries to detect browser's default locale and find if there are appropriate translation string. If it succeeded, browser locale will be used. If fails, it will use English fallback.

Also you can force SDK to always use locale you want. To do this, pass `locale` option to init method.

```javascript
var Notimatica = Notimatica || [];
Notimatica.push(['init', {
  project: 'PROJECT_ID',
  subdomain: 'SUBDOMAIN',
  locale: 'es',
  strings: {
    es: {
      'tooltip.subscribe': 'Suscribirse a las noticias',
    }
  }
}]);
```

With this example SDK will be forced to use Spanish language for every string as long as they are presented. If not, it will use English fallback.

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
