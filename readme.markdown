# deep-equal-ext

Extends [`node-deep-equal`](https://github.com/substack/node-deep-equal) to support comparing these values:

- Function
- RegExp
- Getter
- Setter

**Note that above values are compared by calling `toString()` and matching strings.**

# How To Use

```bash
npm i --save deep-equal-ext
```

```js
import deepEqualExt from 'deep-equal-ext'

const objectA = {
    reg: /\w+/,
    func: function(a, b) { return a + b },
    obj: { a : [ 2, 3 ], b : [ 4 ] },
    get x() {
        return this.mX
    },
    set x(v) {
        this.mX = v
    }
}
const objectB = {
    reg: /\w+/,
    func: function(a, b) { return a + b },
    obj: { a : [ 2, 3 ], b : [ 4 ] },
    get x() {
        return this.mX
    },
    set x(v) {
        this.mX = v
    }
}

deepEqualExt(objectA, objectB) // true
```

