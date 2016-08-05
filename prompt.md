# Prompt plugin

Snappy way to replace default browser subscription prompt. Particularly useful in the case of HTTP site because it can appear automatically using autoSubscribe method.

![prompt](/static/prompt.png "Prompt"){height="200"}

{.toc}
* [Installation](#installation)
* [Options](#options)
* [Strings](#strings)

{#installation}
## Installation

```javascript
var Notimatica = Notimatica || [];
Notimatica.push(['init', {
  project: 'PROJECT_ID',
  plugins: {
    prompt: {
      enable: true
    }
  }
}]);
```

{#options}
## Options

{.table .table-bordered .table-striped}
| Name | Type | Default value | Description |
|------|------|---------------|-------------|
| autorun | Boolean | `true` | Run plugin right after it loaded. Adds ability to run it manually |
| target | String | `'body'` | Selector of the element that will be appended with plugin's html |
| css | String | `Notimatica.options.sdkPath + '/notimatica-prompt.css'` | Where to get css |
| cssTarget | String | `'head'` | Selector of the element that will be appended with plugin's css styles |

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
| `prompt.subscribe` | Do you want to recieve desktop notifications from us? Click Subscribe button! |
| `prompt.button.subscribe` | Subscribe |
| `prompt.button.cancel` | Not now |
