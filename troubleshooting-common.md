# Troubleshooting for Google Chrome

{.toc}
* [Notifications are not showing up on my website](#notifications-are-not-showing-on-website)
* [No notifications in Google Chrome (desktop)](#no-notifications-in-desktop-chrome)
* [No notifications in Google Chrome (mobile)](#no-notifications-in-mobile-chrome)
* [No notifications in Mozilla Firefox](#no-notifications-in-desktop-firefox)
* [Resetting notification permissions and cleaning cache](#resetting-notifications-permissions)
* [Notification icons are not showing up in Apple Safari](#icons-not-showing)

{#notifications-are-not-showing-on-website}
## Notifications are not showing up on my website

Notimatica’s SDK prints handy error messages on the Developer Tools Console if it works in a debug-mode. You can switch it on by adding `debug: true` parameter to `init()` just like this:

{.line-numbers}
```javascript
var Notimatica = Notimatica || [];
Notimatica.push(['init', {
  project: 'PROJECT_ID',
  debug: true
}]);
```
<div class="callout callout-info" role="alert">

#### More Options

Checkout our comprehensive documentation on [JavaScript SDK](/docs/javascript-sdk) with complete list of options.

</div>

To access Developer Tools Console:

**Chrome:** Right click on the page, click Inspect, and click the Console tab.

**Firefox:** Right click on the page, click Inspect element, and click the Console tab.

**Safari:** Go to **Safari → Preferences → Advanced** and make sure Show Develop menu in menu bar is checked. Then right click on the page, click Inspect element, and click the Console.

**Chrome Android:** Debugging on Chrome on Android requires a USB-cable to connect Android device to a computer. Please follow the [Guide for remote debugging in Chrome](https://developer.chrome.com/devtools/docs/remote-debugging)

**Firefox Android:** Debugging on Firefox on Android requires a USB-cable to connect Android device to a computer. Please follow the [Guide for remote debugging in Firefox](https://developer.mozilla.org/en-US/docs/Tools/Remote_Debugging/Debugging_Firefox_for_Android_with_WebIDE)

1. Make sure you are using a [supported browser](/docs/introduction#browsers-support).

1. Check whether you’re not in Private Browsing mode, Incognito mode, Guest browsing mode or using Full-screen mode. 

1. Check whether the following URLs are accessible:

    * `https://site.com/manifest.json`
    * `https://site.com/notimatica-sw.js`

1. Make sure `notimatica-sw.js` is served from the same domain the visitor is currently on and it is not served by a redirect.

{#no-notifications-in-desktop-chrome}
## No notifications in Google Chrome 

### Chrome Desktop

1. Check whether you’re using modern version of Chrome v48+.

1. Check whether you’re not in Incognito mode, Guest browsing mode. Push notifications are not working in these modes.

1. Check whether you’re not in Full-screen mode. Chrome hides notifications in Full-screen mode.

1. Tap the ‘⋮’ menu, **Settings → Advanced → Site settings → Notifications**, make sure it's set to "Ask before sending (recommended)". On the same menu, go to "All sites", find your site and make sure notifications aren't blocked.

{#no-notifications-in-mobile-chrome}
### Chrome Mobile

**If you're using an iOS device:**

Currently Apple does not support web push notifications, only native app notifications.

**If you're using an Android device:**

1. Check whether you’re using modern version of Chrome v42+.

1. Check whether you’re not in Incognito mode or Guest browsing mode. Web push notifications do not work in Incognito and Guest browsing modes.

1. Tap the ‘⋮’ menu, **Settings → Advanced → Site settings → Notifications**, make sure it's set to "Ask before sending (recommended)". On the same menu, go to "All sites", find your site and make sure notifications aren't blocked.

{#no-notifications-in-desktop-firefox}
## No notifications in Mozilla Firefox
1. Check whether you’re using modern version of Firefox v44+.

1. Check whether you’re not in Private Browsing mode. Web push notifications are not working in Private Browsing.

1. Check whether you’re not in Full-screen mode. Firefox hides notifications in Full-screen mode.

{#resetting-notifications-permissions}
## Resetting notification permissions and cleaning cache

If you still can’t get push notifications work then follow these ultimate guide to reset permissions and remove Notimatica’s background worker. Even if all settings are correct at the moment, they could be incorrect in the past and this may affect notifications now.

### Google Chrome (desktop)

1. Click the icon next your site’s URL.

1. Go to **Permission → Notifications** and make sure it is "Use global default (Ask)".

![Google Chrome](/static/troubleshooting/chrome1.png "Google Chrome"){.img-responsive .center-block}

1. Clear site data - Go to *Cookies* and click on "Show cookies and site data" (Windows) or "# from this site" (Mac). Select all the entries at once and click "Remove". No entries should be left.

![Google Chrome](/static/troubleshooting/chrome2.png "Google Chrome"){.img-responsive .center-block}

![Google Chrome](/static/troubleshooting/chrome3.png "Google Chrome"){.img-responsive .center-block}

1. If you have HTTP website go to `https://your-subdomain.notimatica.io` and repeat steps 1-2 for your subdomain URL.

1. Close all tabs and windows with your website or `https://your-subdomain.notimatica.io`.

1. Open a new tab with [chrome://serviceworker-internals/](chrome://serviceworker-internals/) and press "Stop" and "Unregister" under all Scopes that contain your website domain or `https://your-subdomain.notimatica.io`. If you have troubles with removing them, check whether all tabs and windows with your website are closed.

![Google Chrome](/static/troubleshooting/chrome4.png "Google Chrome"){.img-responsive .center-block}

1. Congratulations, you've nailed it! Now open a new tab with your website.

### Firefox

1. Click the icon next your website’s URL.

1. Find notification permissions and change them from "Allow" to "Always Ask".

![Mozilla Firefox](/static/troubleshooting/firefox1.png "Mozilla Firefox"){.img-responsive .center-block}

1. Then on the same dialog, click ">"" and then "More Information".

![Mozilla Firefox](/static/troubleshooting/firefox2.png "Mozilla Firefox"){.img-responsive .center-block}

![Mozilla Firefox](/static/troubleshooting/firefox3.png "Mozilla Firefox"){.img-responsive .center-block}

1. In the popup appeared go to **Permissions → Maintain Offline Storage** and click ‘Clear Storage’.

![Mozilla Firefox](/static/troubleshooting/firefox4.png "Mozilla Firefox"){.img-responsive .center-block}

Well done! Now open close the popup and open new tab with your website.

## Notification icons are not showing up in Apple Safari

On the top menu, go to **Safari → Preferences → Notifications** and remove your website from the list there. Then open a new tab with your website and subscribe to notifications once again. Safari will re-downloaded icons to your system and they will show up in notification prompt.

![Apple Safari](/static/troubleshooting/safari1.png "Apple Safari"){.img-responsive .center-block}