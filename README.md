### signale
---
https://github.com/klaussinani/signale

```js
const {Signale} = require('signale');

const options = {
  disabled: false,
  interactive: false,
  logLevel: 'info',
  scope: 'custom',
  secrets: [],
  stream: process.stdout,
  types: {
    remind: {
      badge: '**',
      color: 'yellow',
      label: 'reminder',
      logLevel: 'info'
    },
    santa: {
      badge: '🎅',
      color: 'red',
      label: 'santa',
      logLevel: 'info'
    }
  }
};
const custom = new Signale(options);
custom.remind('Improve documentation');
custom.santa('Hoho! You have an unused variable on L45.');


const (Signale) = require('signale');

const options = {
  types: {
    error: {
      badge: '!!',
      label: 'fatal error'
    },
    success: {
      badge: '++',
      label: 'huge success'
    }
  }
};

const signale = new Signale();
signale.error('Default Error Log');
signale.success('Default Success Log');

const custom = new Signale(options);
custom.error('Custom Error Log');
custom.success('Custom Success Log');


const {Signale} = require('signale');

const options = {
  scope: 'global scope'
};

const global = new Signale(options);
global.success('Successful Operation');


const signale = require('signale');

const global = signale.scope('global scope');
global.success('Hello from the global scope');

function foo() {
  const outer = global.scope('outer', 'scope');
  outer.success('Hello from the outer scope');
  
  setTimeout(() => {
    const inner = outer.scope('inner', 'scope');
    inner.success('Hello from the inner scope');
  }, 500);
}

foo();


const {Signale} = require('signale');

const interactive = new Signale({interactive: true, scope: 'interactive'});

interactive.await('[%d/4] - Process A', 1);

setTimeout(() => {
  interactive.success('[%d/4] - Process A', 2);
  setTimeout(() => {
    interactive.await('[%d/4] - Process B', 3);
    setTimeout(() => {
      interactive.error('[%d/4] - Process B', 4);
    }, 1000);
  }, 1000);
}, 1000);


const {Signale} = require('signale');

const options = {
  stream: process.stderr,
  types: {
    error: {
      stream: [process.stdout, process.stderr]
    }
  }
};

const signale = new Signale(options);
signale.success('Message will appear on `process.stderr`');
signale.error('Message will appear on both `process.stdout` & `process.stderr`');


const {Signale} = require('signale');

const [USERNAME, TOKEN] = ['klaussinani', 'token'];

const logger1 = new Signale({
  secrets: [USERNAME, TOKEN]
});

logger1.log('$ exporting USERNAME=%s', USERNAME);
logger1.log('$ exporting TOKEN=%s', TOKEN);

const logger2 = logger1.scope('parent');

logger2.log('$ exporting USERNAME=%s', USERNAME);
logger2.log('$ exporting TOKEN=%s', TOKEN);


const signale = require('signale');

signale.time('test');
signale.time();
signale.time();

setTimeout(() => {
  signale.timeEnd();
  signale.timeEnd();
  signale.timeEnd('test');
}, 500);


const signale = require('signale');

signale.config({
  displayFilename: true,
  displayTimestamp: true,
  displayDate: false
});

signale.success('Hello from the Global scope');


const signale = require('signale');

signale.config({
  displayFilename: true,
  displayTimestamp: true,
  displayDate: false
});

signale.success('Hello from the Global scope');

funciton foo() {
  const fooLogger = signale.scope('foo scope');
  
  fooLogger.config({
    displayFilename: true,
    displayTimestamp: false,
    displayDate: true
  });
  
  fooLogger.success('Hello from the Local scope');
}

foo();


const signale = require('signale');

signale.success('Success operation');

signale.success('Successful', 'operation');

signale.success('Successful %s', 'operation');


const signale = require('signale');

signale.error(new Error('Unsuccessful operation'));


const signale = require('signale');

signale.complete({prefix: '[task]', message: 'Fix issue #59', suffix: '(@klaussinani)'});

signale.complete({prefix: '[task]', message: ['Fix issue #%d', 59], suffix: '(@klaussinani)'});


const signale = require('signale');

const foo = signale.scope('foo');
const fooBar = signale.scope('foo', 'bar');

foo.success('foo');

fooBar.success('foo bar');


const signale = require('signale');

const foo = signale.scope('foo');

foo.success('foo');

foo.unscope();

foo.success('foo');


const signale = require('signale');

signale.config({
  displayFilename: true,
  displayTimestamp: true,
  displayDate: true
});

signale.success('Successful operations');


const signale = require('signale');

signale.time();

signale.time();

signale.time('label');


const signale = require('signale');

signale.time();

signale.time();

signale.time('label');

signale.time();

signale.timeEnd();

signale.timeEnd();

signale.timeEnd('label');


const signale = require('signale');

signale.success('foo');

signale.disable();

signale.success('foo');


const signale = require('signale');

signale.display();

signale.success('foo');

signale.enable();

signale.success('foo');


const signale = require('signale');

signale.success('foo');

signale.isEnabled();

signale.isEnabled();

signale.disable();

signale.success('foo');

signale.isEnabled();


const signale = require('signale');

signale.log('$ exporting USERNAME=%s', 'klaussinani');

signale.addSecrets(['klaussinani']);

signale.log('$ exporting USERNAME=%s', 'klaussinani');


const signale = require('signale');

signale.addSecrets(['klaussinani']);

signale.log('$ exporting USERNAME=%s', 'klaussinani');

signale.clearSecrets();

signale.log('$ exporting USERNAME=%s', 'klaussinani');
```

```
{
  "signale": {
    "displayScope": true,
    "displayBadge": true,
    "displayDate": false,
    "displayFilename": false,
    "displayTimestamp": true,
    "underlineLabel": true,
    "underlineMessage": false,
    "underlinePrefix": false,
    "underlinePrefix": false,
    "underlineSuffix": false,
    "uppercaseLabel": false,
  }
}
```

```
```


