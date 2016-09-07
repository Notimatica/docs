# Tagging

Notimatica supports tagging users with additional attributes using the JavaScript SDK API methods. Our tagging model allows you to assign up to 10 tags to each user. 

Tag is a key-value pair of simple string data. Tags could be increadably useful if you want to divide your audience into segments and send web push notifications to a specific segment. 

Here is an example of setting 2 tags for a user while initializing JavaScript SDK:

{.line-numbers}
```javascript
var Notimatica = Notimatica || [];
Notimatica.push(['init', {
  project: 'PROJECT_ID',
  subdomain: 'SUBDOMAIN',
  tags: [
    123456789,
    'registered'
  ]
}]);
```

<div class="callout callout-warning" role="alert">

#### Please Note

Don't send arrays or hashes as a data to set up a tag. Use only simple strings or numbers, otherwise tags won't work.

</div>

The tags will be set to the user once it subscribes to web push notifications.

#### Sending Notifications to Specific Users
There are two ways to send web push notifications to segments:

* Through our [Dashboard](https://my.notimatica.io)
* Using [Server API](https://notimatica.api-docs.io)

##### Sending Notifications via the Dashboard
To target specific segment of your audience, you have to first create a Segment. Add filters matching your key and value.

![Create segment](/static/tagging/segment1.png "Create segment"){.img-rounded .img-shadow .img-responsive .center-block}

After you've created a segment matching at least one user, you can send web push notifications targeting this segment.

![Send to segment](/static/tagging/segment2.png "Send to segment"){.img-rounded .img-shadow .img-responsive .center-block}

##### Sending Notifications via Server API
To send notifications programmatically via Server API, use POST `segments` method to create a segment and after that POST `notifications` method to send notifications targeting certain group of users or a specific user ([check out the documentation](https://notimatica.api-docs.io/)).