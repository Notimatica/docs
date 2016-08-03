# JavaScript SDK Options

Options should be set in `init` function.

```javascript
Notimatica.push(['init', {
  project: 'PROJECT_ID',
  debug: true,
}]);
```

{.table .table-bordered .table-striped}
| Name | Type | Default value | Description |
|------|------|---------------|-------------|
| `project` | String | `null` | Your project UUID <span class="label label-danger">Required</span> |
| `subdomain` | String | `null` | Subdomain to handle HTTP fallback |
| `debug` | Boolean | `false` | Send debug messages to the console |
| `tags` | Array | `[]` | Additional set of tags for the user |
| `autoSubscribe` | Boolean | `false` | Do you want to start subscription process right after page load. For HTTP sites always `false`. |
| `usePopup` | Boolean | `false` | Force subscribing via HTTP fallback popup. For HTTP sites always `true` |
| `popup` | Object | `{ height: 450, width: 550 }` | HTTP fallback popup options. Height and width in pixels |
| `plugins` | Object | `{}` | Map of plugins to enable and their options |
| `strings` | Object | `{}` | Map of localization strings. Mainly used when you want to localize string from plugins |
| `defaultLocale` | String | `'en'` | Default locale to use |
| `matchExactUrl` | Boolean | `true` | URL comparison strategy for opening new tab on notification click |
| `webhooks` | Object | `{}` | Map of webhooks to push for multiple notifications events |
| `webhooksCors` | Boolean | `false` | If your webhooks support CORS requests |
