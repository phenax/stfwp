# Fuck with their mouse pointer/keyboard

This is more on the nodejs side as the browser obviously won't allow it. Also you need to know your target's device for the attack to be a success.

There are a bunch of packages available on npm to allow you to do something like that. A low level and extremely flexible way to do it would be to use [node-ffi](https://github.com/node-ffi/node-ffi/wiki/Node-FFI-Tutorial) which allows you to call native library functions in node.
A more easy to use solution for this is [RobotJS](https://github.com/octalmage/robotjs) which is what we are going to use for the examples.

* Lets say you have a friend and for some reason you want them to know how to use a butt plug (i don't judge). Well, you could tell them to google it. Or... you could google it for them.
```javascript
const robot = require('robotjs');

const delay = duration => new Promise(res => setTimeout(res, duration));

(async function() {
  robot.keyTap('command'); // Open the desktop search (Wont work all the time)
  await delay(500);
  robot.typeString('Google Chrome');
  await delay(500);
  robot.keyTap('enter');
  await delay(1000); // Wait for the browser to load

  robot.keyTap('L', 'control'); // Ctrl+L to ensure that we are in the address bar
  await delay(100);

  robot.typeString('How to use a buttplug?'); // What do you want your victim to know?
  robot.keyTap('enter');
})();
```

* The classic make the mouse go crazy
```javascript
const robot = require('robotjs');

const random = max => (Math.random() * max) % max;
const getRandomCoords = (xMax, yMax) => ({ x: random(xMax), y: random(yMax) });

const { width, height } = robot.getScreenSize();

// Call me Akshay the merciful because I've only moved the mouse 10 times. You can just run it indefinitely.
Array(10).fill(null).forEach(() => {
  const { x, y } = getRandomCoords(width, height);
  robot.moveMouseSmooth(x, y);
});
```
