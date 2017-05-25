[< back](./SETUP.md)


# Enzyme / Mocha / Chai

#### Install
```
npm i -D enzyme mocha chai babel-register
```
ONLY IF React < 15.5, also add...
```
npm i --save-dev react-test-renderer react-dom
```

#### Test NPM Script
```
"test": "mocha test/.setup.js **/*.spec.js"
```

#### Setup File
create this setup file test/.setup.js with the following
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
import MyComponent from 'MyComponent';

// Prep / Setup

describe('MyComponent', () => {
  it('renders without exploding', () => {
    const wrapper = shallow(<MyComponent />);
    expect(wrapper.exists());
  });

  it('should do stuff');
});
```
