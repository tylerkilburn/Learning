[< back](../README.md)

# Mocha / Chai

#### NPM Install
```
npm i -D mocha chai babel-register
```

#### NPM Test Script
```
"test": "mocha test/.setup.js **/*-spec.js"
```

#### Setup File
```
require('babel-register')();
```

#### Unit Tests
```
import { expect } from 'chai';
import MyFeature from 'MyFeature';

// Prep / Setup

describe('MyFeature', () => {
  it('should do stuff');
});
```


# Enzyme / Mocha / Chai

#### NPM Install
```
npm i -D enzyme mocha chai babel-register
```
ONLY IF React <15.5, also add...
```
npm i --save-dev react-test-renderer react-dom
```

#### NPM Test Script
```
"test": "mocha test/.setup.js **/*-spec.js"
```

#### Setup File
```
require('babel-register')();

var jsdom = require('jsdom').jsdom;

var exposedProperties = ['window', 'navigator', 'document'];

global.document = jsdom('');
global.window = document.defaultView;
Object.keys(document.defaultView).forEach((property) => {
  if (typeof global[property] === 'undefined') {
    exposedProperties.push(property);
    global[property] = document.defaultView[property];
  }
});

global.navigator = {
  userAgent: 'node.js'
};

documentRef = document;
```

#### Unit Tests
```
import React from 'react';
import { expect } from 'chai';
import { shallow } from 'enzyme';
import MyFeature from 'MyFeature';

// Prep / Setup

describe('MyFeature', () => {
  it('should do stuff');
});
```
