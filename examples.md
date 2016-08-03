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

* ###### How to set a specific width and height for HTTP prompt?

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

  You can do it by setting `autoSubscribe` to `true`. On HTTPS websites, this instantly triggers browser's native permission prompt.

  ```javascript
  var Notimatica = Notimatica || [];
  Notimatica.push(['init', {
    project: 'PROJECT_ID',
    autoSubscribe: true
  }]);
  ```

  <div class="callout callout-warning" role="alert">

  #### Attention!

  This behaviour is fully disabled for sites that use HTTP popup fallback. Otherwise popup will be blocked by browser.

  </div>

  </div>

</div>
