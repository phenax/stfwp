# SpeechSynthesis API
Speech synthesis api is a gift from Loki. The beauty of a robotic voice saying things it wouldn't/shouldn't is something out of this world.

```javascript
const say = text => new Promise(res => {
  const utterance = new SpeechSynthesisUtterance(text);
  speechSynthesis.speak(utterance);
  utterance.onend = res;
});
```

Now that you have the tool (`say`), be creative.
```javascript
say('Aaah!! Aaaahh!! Fuck me daddy');
```

Or run it in a loop forever for extra embarrassment and confusion.
```javascript
const foreverSay = () => say('Aaah!! Aaaahh!! Fuck me daddy').then(foreverSay);
foreverSay();
```

NOTE: For this one you have to use EXTREME-UGLIFICATION for the text and also stuff like `SpeechSynthesisUtterance` and `speechSynthesis` so that the victim doesn't realize that its related to the speech and turn down their volume or something.

I personally have had great success with this one especially with the loop.
