[< back](./SETUP.md)

# JSDOM

## Install
```
npm i -D JSDOM
```

## Unit Tests
```
import { expect } from 'chai';
import { JSDOM } from 'jsdom';
import MyFeature from 'MyFeature';

describe('JSDOM Tests', () => {
  it('has form values', () => {
    const { document } = (new JSDOM('...')).window;

    const mockForm = document.createElement('form');
    addHiddenInput(document, mockForm, 'partnerCode', 'UNK');
    addHiddenInput(document, mockForm, 'partnerSiteLocation', '0');

    expect(mockForm.childNodes[0].name).to.equal('partnerCode');
    expect(mockForm.childNodes[0].value).to.equal('UNK');
    expect(mockForm.childNodes[1].name).to.equal('partnerSiteLocation');
    expect(mockForm.childNodes[1].value).to.equal('0');
  });
});

```