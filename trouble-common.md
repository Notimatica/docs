# Troubleshooting for Google Chrome

{.toc}
* [Notifications are not showing up on my website](#notifications-are-not-showing-on-website)
* [No notifications in Google Chrome (desktop)](#no-notifications-in-desktop-chrome)
* [No notifications in Google Chrome (mobile)](#no-notifications-in-mobile-chrome)
* [No notifications in Mozilla Firefox](#no-notifications-in-desktop-firefox)
* [Resetting notification permissions and cleaning cache](#resetting-notifications-permissions)
* [Notification icons are not showing up in Apple Safari](#icons-not-showing)

{#notifications-are-not-showing-on-website}
## [Notifications are not showing up on my website](#notifications-are-not-showing-on-website){name="notifications-are-not-showing-on-website"}

Notimatica’s SDK prints handy error messages on the Developer Tools Console it works in a debug-mode. To switch to debug mode you need to add `debug: true` parameter to init() as it was shown in [Installation section](/docs/sdk-installation#initialize-sdk) or [SDK Options]('/docs/sdk-options').

To open the Developer Tools Console, **Context menu of the page → Inspect, → Console tab**.

1. Make sure you are using a supported browser. iOS web push notification are not supported. Microsoft Edge, Internet Explorer, Safari 5.1 on Windows is not supported.

1. Check whether you’re not in Private Browsing mode / Incognito mode / Guest browsing mode or in full screen.

1. Check whether the following URLs are accessible:

    * `https://site.com/manifest.json`
    * `https://site.com/notimatica-sw.js`

1. Make sure `notimatica-sw.js` is served from the same domain the visitor is currently on.

1. Make sure `notimatica-sw.js` is not served by a redirect. This is not allowed by browsers.

{#no-notifications-in-desktop-chrome}
## [No notifications in Google Chrome (desktop)](#no-notifications-in-desktop-chrome){name="no-notifications-in-desktop-chrome"}

1. Check whether you’re using modern version of Chrome v48+.

1. Check whether you’re not in Incognito mode or Guest browsing mode. Web push notifications do not work in Incognito and Guest browsing modes.

1. Check whether you’re not in full screen mode. Chrome hides notifications in full screen mode

1. Tap the ‘...’ menu, **Settings → Advanced → Site settings → Notifications**, make sure it's set to "Ask before sending (recommended)". On the same menu, go to "All sites", find your site and make sure notifications aren't blocked.

{#no-notifications-in-mobile-chrome}
## [No notifications in Google Chrome (mobile)](#no-notifications-in-mobile-chrome){name="no-notifications-in-mobile-chrome"}

If you're using an iOS device:

Currently Apple does not support web push notifications, only native app notifications.

If you're using an Android device:

1. Check whether you’re using modern version of Chrome v42+.

1. Check whether you’re not in Incognito mode or Guest browsing mode. Web push notifications do not work in Incognito and Guest browsing modes.

1. Tap the ‘...’ menu, **Settings → Advanced → Site settings → Notifications**, make sure it's set to "Ask before sending (recommended)". On the same menu, go to "All sites", find your site and make sure notifications aren't blocked.

{#no-notifications-in-desktop-firefox}
## [No notifications in Mozilla Firefox](#no-notifications-in-desktop-firefox){name="no-notifications-in-desktop-firefox"}

1. Click the icon next your website’s URL.

1. Find notification permissions and change them from ‘Allow’ to ‘Always Ask’.

пример

1. Then on the same dialog, click  > and then ‘More Information’.

1. In the popup appeared go to **Permissions → Maintain Offline Storage** and click ‘Clear Storage’.

Well done! Now open close the popup and open new tab with your website.

{#resetting-notifications-permissions}
## [Resetting notification permissions and cleaning cache](#resetting-notifications-permissions)

If you still can’t get web push notifications work then follow these ultimate guide to reset permissions and remove Notimatica’s background worker. Even if all settings are correct at the moment, they could be incorrect in the past and this may affect notifications now.

### Google Chrome (desktop)

1. Click the icon next your site’s URL.

1. Go to **Permissions section → Notifications**. Make sure it is Use global default (Ask). If there is no Permissions section then you have no saved permissions – go to the next step.

пример

1. Clear site data - On this same panel click "Show cookies and site data" (Windows) or "# from this site" (Mac). Select all the entries at once and click "Remove". No entries should be left.

пример

1. If you have HTTP website then go to `https://your-subdomain.notimatica.io` and repeat steps 1-2 for the subdomain URL.

пример

1. Close all tabs and windows with your website or `https://your-subdomain.notimatica.io`.

пример

1. Open a new tab with [chrome://serviceworker-internals/](chrome://serviceworker-internals/) and press 'Stop' and 'Unregister' under all Scopes that contain your website domain or `https://your-subdomain.notimatica.io`. If you have troubles with removing them, check whether all tabs and windows with your website are closed.

пример

1. Congratulations, you've nailed it. Now open a new tab with your website.

## [Notification icons are not showing up in Apple Safari](#icons-not-showing){name="icons-not-showing"}

On the top menu, go to **Safari → Preferences → Notifications tab** and remove your website from the list there. Then open a new tab with your website and subscribe to notifications once again. Safari will re-downloaded icons to your system and they will show up in notification prompt.

пример
