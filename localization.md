# Localization

Every string in SDK can be localized, even text of the HTTP fallback popup, so you can handle multiple languages.

{.toc}
* [Mechanism](#mechanism)
* [Popup](#popup)

{#mechanism}
## [Mechanism](#mechanism){name="mechanism"}

All strings have a unique namespaced ID and can be translated on any language you like.

By default all strings are for `en` language. If you want to overwrite any of them or add your own language, add them to `strings` options like this:

```javascript
var Notimatica = Notimatica || [];
Notimatica.push(['init', {
  project: 'PROJECT_ID',
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
## [Popup](#popup){name="popup"}

HTTP fallback popup can be translated too. They have have `popup` namespace can be found [here](https://github.com/Notimatica/sdk/blob/master/src/sdk/sdk.js#L33)

As you can notice some strings contain `{project}` placeholder. It is a place where project's name will be placed.
