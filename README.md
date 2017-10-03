## Installation

```
$ git clone https://github.com/alloy/babel-7-destructuring-imported-variable-bug.git
$ cd babel-7-destructuring-imported-variable-bug
$ yarn install
```

## Reproduce

```
$ yarn start -s
====================
Compiled source:
====================
"use strict";

var _someModule = require("./some-module");

var Foo = _someModule.NestedObjects.Foo,
    Bar = NestedObjects.Bar;

====================
Runtime exception:
====================
/Users/eloy/tmp/babel-7-destructuring-imported-variable-bug/index.js:6
    Bar = NestedObjects.Bar;
                       ^

ReferenceError: NestedObjects is not defined
    at Object.<anonymous> (/Users/eloy/tmp/babel-7-destructuring-imported-variable-bug/index.js:6:24)
    at Module._compile (module.js:573:30)
    at Module._compile (/Users/eloy/tmp/babel-7-destructuring-imported-variable-bug/node_modules/pirates/lib/index.js:88:24)
    at Module._extensions..js (module.js:584:10)
    at Object.newLoader [as .js] (/Users/eloy/tmp/babel-7-destructuring-imported-variable-bug/node_modules/pirates/lib/index.js:93:7)
    at Module.load (module.js:507:32)
    at tryModuleLoad (module.js:470:12)
    at Function.Module._load (module.js:462:3)
    at Function.Module.runMain (module.js:609:10)
    at Object.<anonymous> (/Users/eloy/tmp/babel-7-destructuring-imported-variable-bug/node_modules/babel-node/lib/_babel-node.js:156:22)
error Command failed with exit code 1.
```
