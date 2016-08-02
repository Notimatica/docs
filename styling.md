# Styling

{.toc}
* [Overview](#overview)
* [Common Classes](#common-classes)

{#overview}
## [Overview](#overview){name="overview"}

Every plugin has its own css file with namespaced classes. So every style can be overwritten.

For example lets look at [Floating button](/docs/floating-button) plugin. It has 2 scss styles:

* [For button](https://github.com/Notimatica/sdk/blob/master/src/plugins/button/button.scss)
* [For popover](https://github.com/Notimatica/sdk/blob/master/src/plugins/button/popover.scss)

Lets imagine we want default subscribing button be white with black bell in it. So we need to overwrite some default classes:

```css
/* Button itself */
.notimatica-plugin-button-subscribe {
  background-color: #fff !important;
}

.notimatica-plugin-button-subscribe:hover {
  background-color: #fff !important;
}

/* Bell and its waves */
.notimatica-plugin-button-bell,
.notimatica-plugin-button-wave-1,
.notimatica-plugin-button-wave-2 {
  fill: #000 !important;
}
```

Here we use `!important` modifier since we know that plugin styles will be loaded after our own css files and this modifier will force browser to use our styles instead of plugin's ones.

{#common-classes}
## [Common Classes](#common-classes){name="common-classes"}

Since every plugin must be independent from the page it runs on and don't affect it either, plugins are provided with some common classes they can use.

{.table .table-bordered .table-striped .table-info}
| Class | Description |
|-------|-------------|
| `.notimatica-reset` | Reset styles to default values |
| `.notimatica-clearfix` | Simple clearfix |
| `.notimatica-fade` | Fade element. With `.in` class makes it appear |
| `.notimatica-pull-left` | Makes element float left |
| `.notimatica-pull-right` | Makes element float right |
