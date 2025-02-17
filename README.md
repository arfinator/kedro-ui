# 🚨 Deprecation Warning 🚨

Kedro-UI has been deprecated. There will be no further active development on this repo. You can continue using [kedro-ui@1.1.7 package](https://www.npmjs.com/package/@quantumblack/kedro-ui) published on npm. However, if you require further changes, please consider forking.

# Kedro UI

[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![npm version](https://badge.fury.io/js/%40quantumblack%2Fkedro-ui.svg)](https://badge.fury.io/js/%40quantumblack%2Fkedro-ui) [![CircleCI](https://circleci.com/gh/quantumblacklabs/kedro-ui.svg?style=svg&circle-token=16d3f559b48b0890a5ee3adbc1d4be0e62f9637d)](https://circleci.com/gh/quantumblacklabs/kedro-ui)

This repo represents a set of UI components that we use in our internal products and applications. It allows us to move at speed i.e. not rewrite the wheel on every new endeavour.

## 👀 Getting Started

### Installation
To install Kedro UI into your project, run the following in your project directory:
```
npm install @quantumblack/kedro-ui
```

### Usage
The **recommended** way to import Kedro UI components is to import each component and the core CSS separately:
```JavaScript
// Core CSS (import once)
import '@quantumblack/kedro-ui/lib/styles/app.css';
// Single component (import in each file you use it)
import Button from '@quantumblack/kedro-ui/lib/components/button';
```
However the quickest way to import Kedro UI components is with a destructured import:
```JavaScript
import { Button } from '@quantumblack/kedro-ui';
```
Doing this [will import the entire library](https://www.blazemeter.com/blog/the-correct-way-to-import-lodash-libraries-a-benchmark), which will increase your bundle size and affect your page load time, so we don't recommend using this method unless you are using [babel-plugin-transform-imports](https://www.npmjs.com/package/babel-plugin-transform-imports) or you don't care about bundle size.

Once you have installed the library and imported a component, you can use it in your project:
```JavaScript
import React from 'react';
import ReactDOM from 'react-dom';
import '@quantumblack/kedro-ui/lib/styles/app.css';
import Button from '@quantumblack/kedro-ui/lib/components/button';

const MyComponent = () => (
  <Button theme='light' size='small' mode='secondary'>Hello world!</Button>
);

ReactDOM.render(<MyComponent />, document.getElementById('root'));
```

#### Loading Webfonts

By default, the 'Titillium Web' font is imported from Google Fonts via `styles/app.css`. If you would prefer not to include this webfont, you can instead use `styles/app-no-webfont.css`, which does not include this font import. If you need more control over font loading (for instance, you might want to add a callback for once the font has loaded), you can import `LoadWebFont` from `utils/webfont.js`, which provides a configurable JS wrapper around the Google [webfontloader](https://github.com/typekit/webfontloader) library. Example usage:

```JavaScript
import '@quantumblack/kedro-ui/lib/styles/app-no-webfont.css';
import LoadWebFont from '@quantumblack/kedro-ui/lib/utils/webfont.js';

LoadWebFont({
  active: function() {
    console.log('Font has been rendered');
  }
})
```
### Running Kedro-UI locally  

Kedro-UI has an interface based on [react-styleguidist](https://react-styleguidist.js.org/docs/getting-started) that allows you to interact with all the components during development. You can run the react-styleguidst server and start interacting with your components with the following command:
```
npm run start
```

## 📚 Documentation

We use styleguidist to document our comments and their usage. To try them out head over [here](https://quantumblacklabs.github.io/kedro-ui/).

## 👋 Contact

This project needs your help! If you have any questions email: opensource@quantumblack.com
