# Examples And Tutorials

<div class="faq">
<input class="faq-search" type="text" placeholder="Type to search...">

* ###### How can I show subscription status on my page?

  <div>

  To retrieve subscription status you can use [`Notimatica.isSubscribed()`](/docs/sdk-api#isSubscribed) method inside `ready` [event](/docs/sdk-events) callback.

  <div class="code-snippet">

  ```markup
  <span id="status"></span>
  ```

  ```javascript
  Notimatica.push(['on', 'ready', function () {
    document.getElementById('status').textContent = Notimatica.isSubscribed()
      ? 'Subscribed'
      : 'Unsubscribed'
  }])
  ```

  </div></div>

* ###### How can I trigger subscription prompt via link?

  <div>

  For this example we will use a `click` HTML event that will be triggered on link click.

  <div class="code-snippet">

  ```markup
  <a href="#" id="subscribe-link">Subscribe</a>
  ```

  ```javascript
  // Function to call on link click
  function subscribe (event) {
    e.preventDefault()
    Notimatica.push(['subscribe'])
  }

  // Define a callback on link click
  document.getElementById('subscribe-link').addEventListener('click', subscribe)
  ```

  </div></div>

* ###### How can I hide subscription link after user successfully subscribes?

  <div>

  In this example we will use `subscribe:success` [event](/docs/sdk-events) to handle successful subscription.

  <div class="code-snippet">

  ```markup
  <a href="#" id="subscribe-link">Subscribe</a>
  ```

  ```javascript  
  // Define a callback on link click
  var link = document.getElementById('subscribe-link')
  link.addEventListener('click', subscribe)

  // Function to call on link click
  function subscribe (event) {
    e.preventDefault()
    Notimatica.push(['subscribe'])
  }

  // Listening successful subscription event and hide the link
  Notimatica.push(['on', 'subscribe:success', function () {
    link.style.display = 'none'
  }])
  ```

  </div></div>

* ###### Is there any way to force HTTPS site to use HTTP fallback popup?

  <div>

  Yes you can do it by setting `usePopup` option while initializing JavaScript SDK.

  ```javascript
  var Notimatica = Notimatica || [];
  Notimatica.push(['init', {
    project: 'PROJECT_ID',
    usePopup: true // Enables popup even if the site is under HTTPS
  }]);
  ```

  </div>

* ###### How to set a specific width and height for HTTP-prompt?

  <div>

  JavaScript SDK lets you to overwrite default popup window size. You can do it by defining `popup` option while initializing JavaScript SDK.

  ```javascript
  var Notimatica = Notimatica || [];
  Notimatica.push(['init', {
    project: 'PROJECT_ID',
    popup: {
      height: 450, // Height of the popup in pixels
      width: 550 // Width of the popup in pixels
    }
  }]);
  ```

  </div>

* ###### How can I automatically prompt users to subscribe?

  <div>

  You can do it by setting `autoSubscribe` to `true`. On HTTPS websites, this instantly triggers browser's native opt-in prompt.

  ```javascript
  var Notimatica = Notimatica || [];
  Notimatica.push(['init', {
    project: 'PROJECT_ID',
    autoSubscribe: true
  }]);
  ```

  <div class="callout callout-warning" role="alert">

  #### Please Note

  This behaviour is fully disabled for sites that use HTTP popup fallback. Otherwise popup will be blocked by a browser.

  </div>

  </div>

* ###### Can I change SDK options in runtime?

  <div>

  Yes. You can do it like this:

  ```javascript
  var Notimatica = Notimatica || [];

  // First init
  Notimatica.push(['init', {
    project: 'PROJECT_ID',
    autoSubscribe: true
  }]);

  // Reset SDK to initial state
  Notimatica.push(['resetSDK']);

  // Init it again but with different options
  Notimatica.push(['init', {
    project: 'PROJECT_ID',
    autoSubscribe: false
  }]);
  ```

  <div class="callout callout-warning" role="alert">

  #### Please Note

  Once you reset SDK, you loose all your event bindings. After reset don't forget to set them again.

  </div>

  </div>

* ###### How can I test SDK functionality without connecting to Notimatica?

  <div>

  You can always emulate this process by setting `emulate` option. It can be useful if you want to test compatibility or our functionality before you connect to us.

  This option makes using Project ID optional so emulation process will be acting like your site is fully HTTPS. So there will be no popup windows.

  ```javascript
  var Notimatica = Notimatica || [];
  Notimatica.push(['init', {
    emulate: true
  }]);
  ```

  </div>

* ###### How to sending yourself a test notification?

  <div>

  Макс?

  </div>

* ###### How to enable debug-mode?

  <div>

   You can switch Notimatica’s SDK into debug-mode by adding `debug: true` parameter to `init()`. After that SDK will start to prints error messages on the Developer Tools Console: 

  {.line-numbers}
  ```javascript
  var Notimatica = Notimatica || [];
  Notimatica.push(['init', {
    project: 'PROJECT_ID',
    debug: true
  }]);
  ```

  </div>

* ###### Tagging

  <div>

  Notimatica supports tagging users. It is especially usefull to send notifications to a specific segments of audience. For example, only to registered users. You can assign up too 10 tags to each user.

  To tag user you have to add `tags` option while initializing SDK.

  Here is an example:

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

  We've added 2 tags to the user. First one (on line #5) is some internal ID, second one is a role (`anonymous`, `registered` or any other you like).

  This tags will be set to the user once he opt-ins to notifications.

  Then in the **Segments** in [Dashboard](https://notimatica.io) you can create a new "Registered" segment where all subscribers with `registered` tag will appear.

 This segment can be used to send particular notifications to a registered users.
  </div>

</div>
