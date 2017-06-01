[< back](./SETUP.md)

# Mocha / Chai

## Install
```
npm i -D mocha chai babel-register
```

## Test NPM Script
```
"test": "mocha test/.setup.js **/*.spec.js"
```

## Setup File ( if using es6 )
* Install babel-core and babel-preset-es2015
* Setup .bablerc with "presets": ["es2015"]
* create this setup file test/.setup.js with the following
```
require('babel-register')();
```

## Unit Tests
```
import { expect } from 'chai';
import MyFeature from 'MyFeature';

// Prep / Setup

describe('MyFeature', () => {
  it('should do stuff');
});
```