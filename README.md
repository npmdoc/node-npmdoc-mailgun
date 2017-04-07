# api documentation for  [mailgun (v0.5.0)](http://github.com/shz/node-mailgun)  [![npm package](https://img.shields.io/npm/v/npmdoc-mailgun.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-mailgun) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-mailgun.svg)](https://travis-ci.org/npmdoc/node-npmdoc-mailgun)
#### Mailgun for Node.js

[![NPM](https://nodei.co/npm/mailgun.png?downloads=true)](https://www.npmjs.com/package/mailgun)

[![apidoc](https://npmdoc.github.io/node-npmdoc-mailgun/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-mailgun_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-mailgun/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-mailgun/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-mailgun/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "shz"
    },
    "bugs": {
        "url": "https://github.com/shz/node-mailgun/issues"
    },
    "dependencies": {},
    "description": "Mailgun for Node.js",
    "devDependencies": {},
    "directories": {},
    "dist": {
        "shasum": "bce0f3134a6d788b6f2368f71784ef20277cd697",
        "tarball": "https://registry.npmjs.org/mailgun/-/mailgun-0.5.0.tgz"
    },
    "engine": "node",
    "homepage": "http://github.com/shz/node-mailgun",
    "main": "./mailgun",
    "maintainers": [
        {
            "name": "shz",
            "email": "lylepstein@gmail.com"
        }
    ],
    "name": "mailgun",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+ssh://git@github.com/shz/node-mailgun.git"
    },
    "version": "0.5.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module mailgun](#apidoc.module.mailgun)
1.  [function <span class="apidocSignatureSpan">mailgun.</span>Mailgun (apiKey)](#apidoc.element.mailgun.Mailgun)
1.  object <span class="apidocSignatureSpan">mailgun.</span>Mailgun.prototype
1.  string <span class="apidocSignatureSpan">mailgun.</span>CAMPAIGN_ID
1.  string <span class="apidocSignatureSpan">mailgun.</span>MAILGUN_TAG

#### [module mailgun.Mailgun](#apidoc.module.mailgun.Mailgun)
1.  [function <span class="apidocSignatureSpan">mailgun.</span>Mailgun (apiKey)](#apidoc.element.mailgun.Mailgun.Mailgun)

#### [module mailgun.Mailgun.prototype](#apidoc.module.mailgun.Mailgun.prototype)
1.  [function <span class="apidocSignatureSpan">mailgun.Mailgun.prototype.</span>_createHttpOptions (resource, method, servername)](#apidoc.element.mailgun.Mailgun.prototype._createHttpOptions)
1.  [function <span class="apidocSignatureSpan">mailgun.Mailgun.prototype.</span>createRoute (pattern, destination, callback)](#apidoc.element.mailgun.Mailgun.prototype.createRoute)
1.  [function <span class="apidocSignatureSpan">mailgun.Mailgun.prototype.</span>deleteRoute (id, callback)](#apidoc.element.mailgun.Mailgun.prototype.deleteRoute)
1.  [function <span class="apidocSignatureSpan">mailgun.Mailgun.prototype.</span>getRoutes (callback)](#apidoc.element.mailgun.Mailgun.prototype.getRoutes)
1.  [function <span class="apidocSignatureSpan">mailgun.Mailgun.prototype.</span>sendRaw (sender, recipients, rawBody)](#apidoc.element.mailgun.Mailgun.prototype.sendRaw)
1.  [function <span class="apidocSignatureSpan">mailgun.Mailgun.prototype.</span>sendText (sender, recipients, subject, text)](#apidoc.element.mailgun.Mailgun.prototype.sendText)



# <a name="apidoc.module.mailgun"></a>[module mailgun](#apidoc.module.mailgun)

#### <a name="apidoc.element.mailgun.Mailgun"></a>[function <span class="apidocSignatureSpan">mailgun.</span>Mailgun (apiKey)](#apidoc.element.mailgun.Mailgun)
- description and source-code
```javascript
Mailgun = function (apiKey) {

  // Authentication uses the api key in base64 form, so we cache that
  // here.
  this._apiKey64 = new Buffer('api:' + apiKey).toString('base64');

  this._apiKey = apiKey;
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.mailgun.Mailgun"></a>[module mailgun.Mailgun](#apidoc.module.mailgun.Mailgun)

#### <a name="apidoc.element.mailgun.Mailgun.Mailgun"></a>[function <span class="apidocSignatureSpan">mailgun.</span>Mailgun (apiKey)](#apidoc.element.mailgun.Mailgun.Mailgun)
- description and source-code
```javascript
Mailgun = function (apiKey) {

  // Authentication uses the api key in base64 form, so we cache that
  // here.
  this._apiKey64 = new Buffer('api:' + apiKey).toString('base64');

  this._apiKey = apiKey;
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.mailgun.Mailgun.prototype"></a>[module mailgun.Mailgun.prototype](#apidoc.module.mailgun.Mailgun.prototype)

#### <a name="apidoc.element.mailgun.Mailgun.prototype._createHttpOptions"></a>[function <span class="apidocSignatureSpan">mailgun.Mailgun.prototype.</span>_createHttpOptions (resource, method, servername)](#apidoc.element.mailgun.Mailgun.prototype._createHttpOptions)
- description and source-code
```javascript
_createHttpOptions = function (resource, method, servername) {
  return {
    host: 'api.mailgun.net',
    port: 443,
    method: method,
    path: '/api/' + resource + (servername ? '?servername=' + servername : ''),

    headers: {
      'Authorization': 'Basic ' + this._apiKey64
    }
  };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mailgun.Mailgun.prototype.createRoute"></a>[function <span class="apidocSignatureSpan">mailgun.Mailgun.prototype.</span>createRoute (pattern, destination, callback)](#apidoc.element.mailgun.Mailgun.prototype.createRoute)
- description and source-code
```javascript
createRoute = function (pattern, destination, callback) {

  // Prep the request.
  var httpOptions = this._createHttpOptions('routes.xml', 'POST');

  // Create the HTTP POST data.
  var data = '' +
  '<route>' +
    '<pattern>' + pattern + '</pattern>' +
    '<destination>' + destination + '</destination>' +
  '</route>';

  // Prep the request.
  var httpOptions = this._createHttpOptions('routes.xml', 'POST');
  httpOptions.headers['Content-Type'] = 'text/xml';
  httpOptions.headers['Content-Length'] = Buffer.byteLength(data);

  // Fire it.
  https.request(httpOptions, function(res) {

    // Collect the data
    var data = '';
    res.on('data', function(c) { data += c });
    res.on('close', function(err) { callback(err) });
    res.on('end', function() { finish() });

    // Handle the results
    var finish = function() {

      if (res.statusCode == 201) {
        var id = xre('id').exec(data)[1];

        callback && callback(undefined, id);
      } else {
        var message = xre('message').exec(data);
        callback && callback(new Error(message ? message[1] : data));
      }
    };
  }).end(data);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mailgun.Mailgun.prototype.deleteRoute"></a>[function <span class="apidocSignatureSpan">mailgun.Mailgun.prototype.</span>deleteRoute (id, callback)](#apidoc.element.mailgun.Mailgun.prototype.deleteRoute)
- description and source-code
```javascript
deleteRoute = function (id, callback) {

  // Prep the request
  var httpOptions = this._createHttpOptions('routes/' + id + '.xml', 'DELETE');
  httpOptions.headers['Content-Type'] = 'text/xml';
  httpOptions.headers['Content-Length'] = 0;

  // Fire it.
  https.request(httpOptions, function(res) {

    if (res.statusCode == 200) {
      callback && callback(undefined);
    } else {
      var data = '';
      res.on('data', function(c) { data += c });
      res.on('close', function(err) { callback(err) });
      res.on('end', function() {
        var message = xre('message').exec(data);
        callback && callback(new Error(message ? message[1] : data))
      });
    }
  }).end();
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mailgun.Mailgun.prototype.getRoutes"></a>[function <span class="apidocSignatureSpan">mailgun.Mailgun.prototype.</span>getRoutes (callback)](#apidoc.element.mailgun.Mailgun.prototype.getRoutes)
- description and source-code
```javascript
getRoutes = function (callback) {

  // Some sanity checking.  It makes no sense to call this without a
  // callback.
  if (typeof callback != 'function') throw new Error('Callback must be a function');

  // Prep the request.
  var httpOptions = this._createHttpOptions('routes.xml', 'GET');

  // Fire it.
  https.request(httpOptions, function(res) {

    // Check for failure
    if (res.statusCode != 200)
      return callback(res.statusCode);

    // We're going to be a little lazy and just eat up all the data
    // before parsing it.
    var data = '';
    res.on('data', function(c) {
      data += c;
    });

    // Handle catastrophic failures with an error
    res.on('close', function(err) {
      // FIXME - In some cases this could cause the callback to be called
      //         with an error, even after we called it successfully.
      callback(err.code);
    });

    // Once the request is done, we have all the data and can parse it.
    res.on('end', function() {

      // Silly XML parsing because I don't want to include another
      // dependency.  Fortunately the structure is very simple and
      // convenient to parse with this method.
      var routes = data.replace(/\s/g, '').match(xre('route'));
      var nroutes = [];
      for (var i=0; i<routes.length; i++) {

        // Pull the route out, since we're going to change it.
        var route = routes[i];

        // Pull the data.
        var r = {};
        r.pattern = xre('pattern').exec(route)[1];
        r.destination = xre('destination').exec(route)[1];
        r.id = xre('id').exec(route)[1];
        nroutes.push(r);
      }

      // Send the data to the callback.
      callback(undefined, nroutes);

    });
  }).end();
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mailgun.Mailgun.prototype.sendRaw"></a>[function <span class="apidocSignatureSpan">mailgun.Mailgun.prototype.</span>sendRaw (sender, recipients, rawBody)](#apidoc.element.mailgun.Mailgun.prototype.sendRaw)
- description and source-code
```javascript
sendRaw = function (sender, recipients, rawBody) {

  // These are flexible arguments, so we define them here to make
  // sure they're in scope.
  var servername = '';
  var callback = null;

  // Less than 3 arguments means we're missing something that prevents
  // us from even sending an email, so we fail.
  if (arguments.length < 3)
    throw new Error('Missing required argument');

  // Flexible argument magic!
  var args = Array.prototype.slice.call(arguments, 3);
  // Pluck servername.
  if (args.length && typeof args[0] == 'string')
    servername = args.shift() || servername;
  // Pluck callback.
  if (args.length && typeof args[0] == 'function')
    callback = args.shift() || callback;
  // Don't be messy.
  delete args;

  // We allow recipients to be passed as either a string or an array,
  // but normalize to to an array for consistency later in the
  // function.
  if (typeof(recipients) == 'string')
      recipients = [recipients];

  // Mailgun wants its messages formatted in a special way.  Why?
  // Who knows.
  var message = sender +
                '\n' + recipients.join(', ') +
                '\n\n' + rawBody;

  // Prepare the APi request.
  var httpOptions = this._createHttpOptions('messages.eml', 'POST', servername);
  httpOptions.headers['Content-Type'] = 'text/plain; charset=utf-8';
  httpOptions.headers['Content-Length'] = Buffer.byteLength(message);

  // Fire it.
  var req = https.request(httpOptions, function(res) {

    // If the user supplied a callback, fire it and set 'err' to the
    // status code of the request if it wasn't successful.
    if (callback) callback(res.statusCode != 201 ? new Error(res.statusCode) : undefined);
  });

  // Wrap up the request by sending the message, which contains the
  // actual email data we want to send.
  req.end(message);

}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mailgun.Mailgun.prototype.sendText"></a>[function <span class="apidocSignatureSpan">mailgun.Mailgun.prototype.</span>sendText (sender, recipients, subject, text)](#apidoc.element.mailgun.Mailgun.prototype.sendText)
- description and source-code
```javascript
sendText = function (sender, recipients, subject, text) {

  // These are flexible arguments, so we define them here to make
  // sure they're in scope.
  var servername = '';
  var options = {};
  var callback = null;

  // Less than 4 arguments means we're missing something that prevents
  // us from even sending an email, so we fail.
  if (arguments.length < 4)
    throw new Error('Missing required argument');

  // Flexible argument magic
  var args = Array.prototype.slice.call(arguments, 4);
  if (args.length && typeof args[0] == 'string')
    servername = args.shift() || servername;
  if (args.length && typeof args[0] == 'object')
    options = args.shift() || options;
  if (args.length && typeof args[0] == 'function')
    callback = args.shift() || callback;

  // We allow recipients to be passed as either a string or an array,
  // but normalize to to an array for consistency later in the
  // function.
  if (typeof(recipients) == 'string')
      recipients = [recipients];

  // Build the HTTP POST body text.
  var body = querystring.stringify({
    sender: sender,
    recipients: recipients.join(', '),
    subject: subject,
    body: text
  });
  if(options && options !== {})
    body.options = JSON.stringify(options);

  // Prepare our API request.
  var httpOptions = this._createHttpOptions('messages.txt', 'POST', servername);
  httpOptions.headers['Content-Type'] = 'application/x-www-form-urlencoded';
  httpOptions.headers['Content-Length'] = Buffer.byteLength(body);

  // Fire the request to Mailgun's API.
  var req = https.request(httpOptions, function(res) {

    // If the user supplied a callback, fire it and set 'err' to the
    // status code of the request if it wasn't successful.
    if (callback) callback(res.statusCode != 201 ? new Error(res.statusCode) : undefined);
  });

  // Wrap up the request by sending the body, which contains the
  // actual email data we want to send.
  req.end(body);
}
```
- example usage
```shell
...
### Example

Here's a complete sending example.

var Mailgun = require('mailgun').Mailgun;

var mg = new Mailgun('some-api-key');
mg.sendText('example@example.com', ['Recipient 1 <rec1@example.com>', 'rec2@example.com'],
  'This is the subject',
  'This is the text',
  'noreply@example.com', {},
  function(err) {
    if (err) console.log('Oh noes: ' + err);
    else     console.log('Success');
});
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
