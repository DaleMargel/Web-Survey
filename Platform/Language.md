# Platform Language
Of course this refers to javascript.

What version of javascript/typescript to use? This is really a question of how much pain you wish to accept to support older browsers such as IE.

Javascript versions are confusing. The versions here are based on this [link](https://codeburst.io/javascript-wtf-is-es6-es8-es-2017-ecmascript-dca859e4821c) and on this [link](http://2ality.com/2018/02/ecmascript-2019.html) which has a lot of good information plus some good **electronic books on JavaScript**.

Information current as of 2020.07.24

| Version | Year | Main features |
| ------- | ---- | ------------- |
| ES1 | 1997 | First Edition |
| ES2 | 1998 | Editorial changes |
| ES3 | 1999 | Regular Expressions, try/catch | 
| ES4 |      | Abandoned due to internal politics |
| ES5 | 2009 | [Supported on 99.3% of browsers.](https://caniuse.com/#feat=es5) Features include Function.prototype.bind, Array methods like indexOf, forEach, map & filter, Object methods like defineProperty, create & keys, the trim method on Strings and many more.<br><br>**TLDR; Offers only basic language features but is widely supported.** |
| ES5.1 | 2011 | Editorial changes |
| ES6/ES2015 | 2015 | [Supported on 97.8% of browsers.](https://caniuse.com/#feat=es6) Features include Promises, Modules, Classes, Template Literals, Arrow Functions, Let and Const, Default Parameters, Generators, Destructuring Assignment, Rest & Spread, Map/Set & WeakMap/WeakSet and many more.<br><br>**TLDR; This is a major upgrade to ES5. It adds modern language features that are needed by many frameworks. Browser support is only slightly less that ES5.** |
| ES2016 | 2016 | Supported on about 94% of browsers, depending on feature. Features are Array.prototype.includes (95.4%) and Exponentiation Operator (92.5%) |
| ES2017 | 2017 | Features include async, await, some object methods, string padding, shared memory.<br><br>**TLDR; Adds some features that helps developers write better code.** |
| ES2018 | 2018 | Features include asynchronous iteration, promise.finally(), rest/spread, augmented more regular expressions, template literals tweaks |
| ES2019 | 2019 | Features include flatMap, object.fromEntries() |

## Advice
It appears that 75% of users are on an evergreen browser. These support the most recent versions of javascript. For more information explore [CanIUse](https://caniuse.com/#home).

| Version | Advice |
| ---- | ------ |
| ES1-4 | Obsolete. Over 20 years old, do not use |
| ES5  | Use when wide browser support is VERY important. ES5 lacks many modern language features that are needed by most frameworks, so the code will likely have to be transpiled from a higher version of javascript. This can bloat the code and introduce subtle bugs. [This article explains it](https://medium.freecodecamp.org/you-might-not-need-to-transpile-your-javascript-4d5e0a438ca) (2017). At best, you might increase browser support by 1%-2%. It is worth it? You be the judge.  |
| ES6/ES2015 | Use this to obtain a balance of modern language features and wide browser support. This version is a major upgrade to javascript and the minimum version that I think should be deployed to the web. |
| ES2017 | This version adds some features that advanced developers would want to use. This might not be quite as widely supported, but the developers experience is wonderful. |
| ES2018+ | Mostly esoteric additions. Use it if you need it. |

Overall, in my opinion (as of mid 2020):
- Normally use ES2017 standards
- If you need a newer features, then use them.
- Write or transpile to ES2015 if you are concerned with browser support.
- Do not transpile to ES5 if it can be avoided.
- If in doubt, check [caniuse.com](https://caniuse.com/).

If the marketing department insists on the widest browser support then choose a technology that supports ES5 (many good ones do!). Otherwise transpile to ES5 but as a separate application. This way your regular users do not pay for those that are still using obsolete browsers. You might also have success with isomorphic rendering or Server Side Rendering (SSR).

## Typescript or Javascript?
I have no strong opinion here. Typescript brings type safety to javascript but makes the toolchain slightly more complicated. For smaller applications, javascript is fine. For large applications, typescript might be better.

For now, we will assume javascript.

[Next> Platform / Rendering Engine](Rendering.md)