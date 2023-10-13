# no-sleep

Prevent display sleep and enable wake lock in all Android and iOS web browsers.

Initially written by [Rich Tibbet](https://github.com/richtr/NoSleep.js)

## Installation

This package is published to npm as **@zakj/no-sleep** and can be installed
with:

`npm install @zakj/no-sleep`

## Build from source

Install all development dependencies with:

`pnpm install`

To build this library run:

`pnpm run build`

## Usage

Import ES6 module:

```javascript
import NoSleep from '@zakj/no-sleep';
```

Create a new NoSleep object and then enable or disable it when needed.

To create a new NoSleep object:

```javascript
var noSleep = new NoSleep();
```

To enable wake lock:

**NOTE: This function call must be wrapped in a user input event handler e.g. a
mouse or touch handler**

```javascript
// Enable wake lock.
// (must be wrapped in a user input event handler e.g. a mouse or touch handler)
document.addEventListener(
  'click',
  function enableNoSleep() {
    document.removeEventListener('click', enableNoSleep, false);
    noSleep.enable();
  },
  false,
);
```

To disable wake lock:

```javascript
// Disable wake lock at some point in the future.
// (does not need to be wrapped in any user input event handler)
noSleep.disable();
```
