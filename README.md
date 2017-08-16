# sails-hook-custom-blueprints

A Sails 1.x hook to re-enable custom blueprint definitions.

### Installation

`npm install sails-hook-custom-blueprints --save`

### Usage

Add your custom blueprint files to your app under `api/blueprints`.

Officially supported file names are:

* find.js
* findOne.js
* create.js
* update.js
* destroy.js
* add.js
* remove.js
* replace.js
* populate.js


But note that you can also add files to inject your _own custom blueprint actions_, such as `search.js`.


##### Routing

For built-in blueprint actions that have corresponding shadow (blueprint) routes, if you have those shadow (blueprint) routes enabled, then your custom blueprint action overrides will be used automatically.

Whether you have shadow (blueprint) routes enabled or not, you can hook up a any blueprint action (including your own custom ones) via an explicit route.  For example:

```js
'GET /foo': { action: 'user/search' },
'GET /bar': { action: 'parrot/search' },
'GET /baz': { action: 'parrot/findOne' },
'GET /bing': { action: 'treasure/find' },
'GET /bong': { action: 'dresser/search' },
'POST /beep': { action: 'treasure/create' },
'DELETE /boop': { action: 'parrot/destroy' },
```
