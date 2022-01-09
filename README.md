# banglejs-2-analog-clock-construction-kit #

a simple "kit" to easily construct individual analog clocks for a Bangle.js 2

Developing an "analog clock" for the [Bangle.js 2](https://www.espruino.com/Bangle.js2) may not be too complicated - but it still requires some knowledge of JavaScript in general and the [Bangle.js environment](https://www.espruino.com/Reference) in particular.

And quite often, an existing clock already comes quite close to what one would like to see - wouldn't there be the small missing detail one cannot live without...

This kit tries to simplify development and customization of such clocks by splitting the implementation into commonly seen parts and providing a framework into which all these parts fit.

As a consequence, people may easily combine already existing (and tested) parts in order to get the desired clock and - if this approach is not already sufficient - to customize or implement only those parts which cannot yet be found elsewhere.

## Common Structure of an Analog Clock ##

The typical structure of an analog clock looks as follows:

```
  let ClockMechanics = require('https://raw.githubusercontent.com/rozek/banglejs-2-simple-clock-mechanics/main/ClockMechanics.js');

  ClockMechanics.windUp({
    size:      require('https://raw.githubusercontent.com/rozek/banglejs-2-smart-clock-size/main/ClockSize.js'),
    background:null,
    face:      require('https://raw.githubusercontent.com/rozek/banglejs-2-twelve-fold-face/main/ClockFace.js'),
    hands:     require('https://raw.githubusercontent.com/rozek/banglejs-2-rounded-clock-hands/main/ClockHands.js'),
    complications:{
      b:require('https://raw.githubusercontent.com/rozek/banglejs-2-date-complication/main/Complication.js')
    }
  },{ withDots:true, seconds:'#FFFF00' });
```

This code implements the following clock:

![](simple-clock-example.png)
