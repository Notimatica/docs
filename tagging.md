# Tagging

To track you users we introduce you a tagging model. You can assign up too 10 tags to your customers.

This may be useful if you want to send messages only to specific segments. For example only to registered users.

To tag user you have to add `tags` option while initializing SDK like this:

{.line-numbers}
```javascript
var Notimatica = Notimatica || [];
Notimatica.push(['init', {
  project: 'PROJECT_ID',
  tags: [
    123456789,
    'registered'
  ]
}]);
```

Here we added 2 tags to your customer. First one (on line #5) is his internal ID in your system, second is his role (`anonymous`, `registered` or any other you have).

This tags will be set to the user once he subscribes to notifications.

Then in the **Segments** section in admin panel you can create a new **Registered** segment where all subscribers with `registered` tag will appear.

In future, this segment can be used by you in notification sending to reach only registered users.
