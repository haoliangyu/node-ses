# [DEPRECATED] node-ses-any-promise

This is a fork of [node-ses](https://github.com/aheckmann/node-ses) with [any-promise](https://github.com/kevinbeaty/any-promise) support. No feature is added or removed.

All functions that require callback function in the original project now return a promise:

``` javascript
// register your favorite promise library, default would be the native global promise
require('any-promise/register/bluebird');

var ses = require('node-ses-any-promise');
var client = ses.createClient({ key: 'key', secret: 'secret' });

// Give SES the details and let it construct the message for you.
client.sendEmail({
  to: 'aaron.heckmann+github@gmail.com',
  from: 'somewhereOverTheR@inbow.com',
  cc: 'theWickedWitch@nerds.net',
  bcc: ['canAlsoBe@nArray.com', 'forrealz@.org'],
  subject: 'greetings',
  message: 'your <b>message</b> goes here',
  altText: 'plain text'
};
.then(function(data, res) {
  // do something
})
.catch(function(err) {
  // do something
});

// ... or build a message from scratch yourself and send it.
client.sendRawEmail({
  from: 'somewhereOverTheR@inbow.com',
  rawMessage: rawMessage
})
.then(function(data, res) {
  // do something
})
.catch(function(err) {
  // do something
});
```

For more detial, see the documentation of `node-ses` and `any-promise`.

## Licence

[MIT](https://github.com/haoliangyu/node-ses-any-promise/blob/master/LICENSE)
