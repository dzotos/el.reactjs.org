---
id: javascript-environment-requirements
title: JavaScript Environment Requirements
layout: docs
category: Reference
permalink: docs/javascript-environment-requirements.html
---

Το React 16 βασίζεται στους collection types [Map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map) και [Set](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set). Σε περίπτωση που υποστηρίζετε παλιότερους browsers και συσκευές που δεν παρέχουν αυτές τις υλοποιήσεις (π.χ. IE < 11) ή δεν ειναι συμβατές (π.χ. IE 11), εξετάστε το ενδεχόμενο να συμπεριλάβετε ένα global polyfill στο bundle της εφαρμογής σας, όπως για παράδειγμα το [core-js](https://github.com/zloirock/core-js) ή το [babel-polyfill](https://babeljs.io/docs/usage/polyfill/).

Ένα polyfilled περιβάλλον για το React 16 με χρήση του core-js που να υποστηρίζει παλιότερους browsers ενδέχεται να μοιάζει κάπως έτσι :

```js
import 'core-js/es6/map';
import 'core-js/es6/set';

import React from 'react';
import ReactDOM from 'react-dom';

ReactDOM.render(
  <h1>Hello, world!</h1>,
  document.getElementById('root')
);
```

Το React επίσης βασίζεται στο `requestAnimationFrame` (ακόμα και σε περιβάλλον test).
Μπορείτε να χρησιμοποιήσετε το [raf](https://www.npmjs.com/package/raf) πακέτο για να καλέσετε το `requestAnimationFrame`:

```js
import 'raf/polyfill';
```
