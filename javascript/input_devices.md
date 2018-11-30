# Fuck with their mouse pointer/keyboard

This is more on the nodejs side as the browser obviously won't allow it. Also you need to know your target's device for the attack to be a success.

There are a bunch of packages available on npm to allow you to do something like that. A low level and extremely flexible way to do it would be to use [node-ffi](https://github.com/node-ffi/node-ffi/wiki/Node-FFI-Tutorial) which allows you to call native library functions in node.
A more easy to use solution for this is [RobotJS](https://github.com/octalmage/robotjs) which is what we are going to use for the examples.

* Lets say you have a friend and for some reason you want them to know how to use a butt plug. Well, you could tell them to google it. Or... you could google it for them.
```javascript
const robot = require('robotjs');

```

