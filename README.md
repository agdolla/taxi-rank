# taxi-rank

A super fast JSDom based Selenium Webdriver API. Write end to end tests once and run them against this super fast, headless browser built on node.js, then once those tests pass you can run them against real browsers in the cloud!

[![Build Status](https://img.shields.io/travis/ForbesLindesay/taxi-rank/master.svg)](https://travis-ci.org/ForbesLindesay/taxi-rank)
[![Dependency Status](https://img.shields.io/david/ForbesLindesay/taxi-rank/master.svg)](http://david-dm.org/ForbesLindesay/taxi-rank)
[![NPM version](https://img.shields.io/npm/v/taxi-rank.svg)](https://www.npmjs.org/package/taxi-rank)

## Installation

```
npm install taxi-rank -g
```

## Usage

In a separate terminal, run `taxi-rank`, then you can use cabbie (or your webdriver client of choice), to connect to this supper-fast virtual driver:

```js
import assert from 'assert';
import cabbie from 'cabbie-sync';

// connect to taxi-rank, adding {debug: true} makes cabbie log each method call.
const driver = cabbie('http://localhost:9516', {debug: true});

try {
  // navigate to a url in the currently active window
  driver.browser.activeWindow.navigator.navigateTo('http://example.com');

  // get an element, and check that its text equals some expected value
  assert.equal(
    driver.browser.activeWindow.getElement('h1').getText(),
    'Example Domain',
  );
} finally {
  // whether tests pass or fail, dispose of the driver
  driver.dispose();
}
```

## License

MIT
