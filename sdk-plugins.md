# JavaScript SDK Plugins System

SDK can easily be extended with plugins. Good example is [Floating button](/docs/floating-button) that was made as a UI element to simplify subscription process.

Every plugin must be an instance of `AbstractPlugin` and should have this methods:

```javascript
/**
 * Plugin name.
 *
 * @return {String}
 */
get name () {
  return 'plugin-name'
}
/**
 * Default options.
 *
 * @return {Object}
 */
get defaults () {
  return {
    autorun: true // Can be set to false to disable automatic startup of the plugin
    target: 'body', // Target on the page where to put plugin template
    css: this.options.sdkPath + '/notimatica-button.css', // If plugin has css, where to search for it
    cssTarget: 'head' // Target on the page where to place css
  }
}
/**
 * Default english strings.
 *
 * @return {Object}
 */
get strings () {
  return {
    en: {}
  }
}
/**
 * Widget template.
 *
 * @return {String}
 */
get template () {
  return '<div class="notimatica-reset notimatica-plugin-wrapper"></div>'
}
/**
 * Play.
 */
play () {}
```

Default options will be merged with user specified so everything can me overwritten.

<div class="callout callout-warning" role="alert">

#### Note!

Template's parent node should always have `notimatica-reset` and `notimatica-plugin-wrapper` classes (as in example above).

First [resets](/docs/styling#common-classes) page styles, second used to interact with the plugin's template in the future.

</div>

Full example of how it works can be found [here](https://github.com/Notimatica/sdk/blob/master/src/plugins/button/plugin.js).
