[< back](./SETUP.md)

# Mocha / Chai

#### NPM Install
```
npm i -D mocha chai babel-register
```

#### NPM Test Script
```
"test": "mocha test/.setup.js **/*.spec.js"
```

#### Setup File
create this setup file test/.setup.js with the following
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