*This repository is a mirror of the [component](http://component.io) module [component/router](http://github.com/component/router). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/component-router`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*

# router

  Simple client-side router.

## Installation

    $ component install component/router

## Examples

  Example with only setup callbacks:

```js
var Router = require('router');

var router = new Router;

router.get('/user/:id', function(id){
  console.log('show %s', id);
});

router.dispatch('/user/2');
```

  Setup and teardown callbacks for unbinding
  events etc:

```js
var Router = require('router');

var router = new Router;

router.get('/user/:id', function(id){
  console.log('show %s', id);
}, function(id){
  console.log('hide %s', id);
});

router.dispatch('/user/2');
router.dispatch('/user/5');
router.dispatch('/user/10');
```

  Fluent api equivalent of above:

```js
var Router = require('router');

var router = new Router;

router.get('/user/:id')
.before(function(id){
  console.log('show %s', id);
})
.after(function(id){
  console.log('hide %s', id);
});

router.dispatch('/user/2');
router.dispatch('/user/5');
router.dispatch('/user/10');
```

## License

  MIT
