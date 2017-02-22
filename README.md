# babel-plugin-transform-closure-strip-annotations

> Strip all [closure annotations](https://github.com/google/closure-compiler/wiki/Annotating-JavaScript-for-the-Closure-Compiler) from your output code.

## Example

**In**

```javascript
import MDCFoundation from './foundation.js';
import MDCIconToggleAdapter from './adapter';

/**
 * @extends {MDCFoundation<!MDCIconToggleAdapter>}
 */
export default class MDCIconToggleFoundation extends MDCFoundation {
  /**
   * @return {!Object<string, string>}
   */
  static get cssClasses() {
    return {
      ROOT: 'mdc-icon-toggle',
      DISABLED: 'mdc-icon-toggle--disabled',
    };
  }
}
```

**Out**

```javascript
import MDCFoundation from './foundation.js';

/**
 * @extends {MDCFoundation<!MDCIconToggleAdapter>}
 */
export default class MDCIconToggleFoundation extends MDCFoundation {
  /**
   * @return {!Object<string, string>}
   */
  static get cssClasses() {
    return {
      ROOT: 'mdc-icon-toggle',
      DISABLED: 'mdc-icon-toggle--disabled',
    };
  }
}
```

## Installation

```sh
npm install --save-dev babel-plugin-transform-closure-strip-annotations
```

## Usage

### Via `.babelrc` (Recommended)

**.babelrc**

```json
{
  "plugins": ["transform-closure-strip-annotations"]
}
```

### Via CLI

```sh
babel --plugins transform-closure-strip-annotations script.js
```

### Via Node API

```javascript
require("babel-core").transform("code", {
  plugins: ["transform-closure-strip-annotations"]
});
```
