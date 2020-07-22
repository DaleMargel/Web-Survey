# Platform Rendering Engine
How to convert your code to a web page.

This is a HUGE topic and there are a great number of products that do this. At it's core, most of these take an annotated html template and inject data into it. How this is done can vary widely. The short list below are the notable ones plus a few that I really like.

For a real-life comparisons of the various frameworks, look at [ToDo MVC](http://todomvc.com/). For even better PWA-specific comparisons look at [HackerNews PWA](https://hnpwa.com/). There are a lot of comparison sites for React, Vue, Angular. Here is [one of them](https://www.codeinwp.com/blog/angular-vs-vue-vs-react/).

| Product | Stars | Description |
| ------- | -----:| ----------- |
| [Vue](https://github.com/vuejs/vue) | ★168k | "a progressive framework for building user interfaces." |
| [React](https://github.com/facebook/react) | ★153k | "A declarative, efficient, and flexible JavaScript library for building user interfaces." |
| [Angular](https://github.com/angular/angular.js) | ★63.5k | "Angular is a development platform for building mobile and desktop web applications using TypeScript/JavaScript and other languages" |
| [Svelte](https://github.com/sveltejs/svelte)⚑  | ★35.6k | "a compiler that takes your declarative components and converts them into efficient JavaScript that surgically updates the DOM"|
| [Preact](https://github.com/preactjs/preact)💗 | ★26.7k | A lighweight version of React |
| [Polymer](https://github.com/Polymer/polymer) | ★21.4k| The most successful Web Component library (until it was killed by W3C) |
| [Heresy](https://github.com/WebReflection/heresy)💗 | ★218| "React-like Custom Elements via the V1 API built-in extends. Also available for SSR." |

## Vue
By github stars, this is the most popular framework. It was released in 2014 as a lighter alternative to Angular. I must admit that I have no experience with it. It uses a combination of annotated html and declarative javascript to bind data to the web page. I understand that it is very popular in China, but not as much in North America.

## React
By media reports, this is the most popular framework by far. It is certainly the best supported. It has been around since 2013.

React is powered by JSX, an XML-like extension to javascript. This allows javascript and html to be intermixed with wild abandon. As hugely popular as it is, it does have a few quirks:

- It uses JSX, which requires a build step to convert to javascript.
- It seems to prefer targeting ES5.
- It uses virtual DOM difference to optimise updates.
- It tends to change its favoured approach from time to time.
- It has its own events, not those of the browser.
- It generates large run-time bundles.

The currently favoured approach is hooks. This is a brilliant way to decouple the user interface from the data. React offers a number of hooks but there are some [third party libraries](https://github.com/streamich/react-use) that take it to an extreme.

## Angular
This was released in 2010 but underwent a major change in 2016. While not as popular as React and Vue, it is popular with big companies and therefore there are a lot of jobs for Angular programmers. It presents a more structured MVC programming model that has a higher learning curve than the others. It also uses Typescript and needs to be compiled to javascript. It generates the largest bundles of the tools listed here.

## Svelte
This framework seems to come up a lot. It was released in 2016. It reads annotated xhtml with javascript and compiles it into a focused light-weight vanilla js web application. I have not used this, but it looks promising.

## Preact
Preact is a lightweight and faster version of React. It has no virtual DOM, it uses the browser events and it removes those lesser-used features that take up space. Because of this, it imposes a 3kb overhead compared to React's 136kb (minified). Preact also has a compatibility library that implements the missing React features if you need them.

If combined with [HTM](https://github.com/developit/htm) the code may run directly in the brower with no compile step. This is why I like it so much.

## Polymer
This was Google's Web Component approach until the W3C decided not to support html imports. This was a key requirement of WC and it stopped the Polymer project in its tracks. In response:

- RIP Web Components.
- A sub set, Custom Elements (et al) can be accessed through javascript.
- The Polymer team wrote lit-html to work with Custom Elements

Polymer used to be my preferred approach until Web Components were killed by W3C. The Polymer team started working with lit-html, but I found that HyperHTML was already a more capable and mature replacement for lit-html so I moved over to [WebReflection](https://github.com/WebReflection). See below.

## Heresy
Heresy used to be the most recent in a long line of experiments by [WebReflection](https://github.com/WebReflection). I took this one for a serious test drive and really liked it. However, like a teenager with OCD, Andrea has since moved on and created several more (awesome) experiments. None of these sit long enough to accumulate a lot of github stars, but no matter. There is some amazing work here; his github page is like a developer candy store.

With over a dozen ways to write a web site, Andrea was kind enough to create a guide [look here](https://gist.github.com/WebReflection/761052d6dae7c8207d2fcba7cdede295). There is also a picker application that lets you choose the best option according to what you want. Most of these support IE11 out of the box.

From his own [web site](https://gist.github.com/WebReflection/761052d6dae7c8207d2fcba7cdede295). Stars current as of 2020.07.22/sorted.

| Product | Stars | Description |
| ------- | -----:| ----------- |
| [hyperHTML](https://github.com/WebReflection/hyperHTML) | ★2.7k | "HTML/SVG with no auto-keyed but optional manually keyed render" |
| [lighterhtml](https://github.com/WebReflection/lighterhtml) | ★552  | "HTML/SVG auto-keyed and manual keyed render" |
| [heresy/ssr](https://github.com/WebReflection/heresy) | ★218 | "lighterhtml + augmentor + Custom Elements" |
| [neverland](https://github.com/WebReflection/neverland) | ★199 | "lighterhtml + dom-augmentor" |
| [wikedElements](https://github.com/WebReflection/wicked-elements)| ★189 | "custom elements without custom elements ... *wait, what?*" |
| [HyperHTMLElement](https://github.com/WebReflection/hyperHTML-Element) | 162 | "custom elements via hyperHTML" |
| [µhtml](https://github.com/WebReflection/uhtml) | ★154 | "HTML/SVG auto-keyed and manual keyed render" |
| [augmentor](https://github.com/WebReflection/augmentor) | ★91 | "augmentor (hooks for anything)" |
| [µce](https://github.com/WebReflection/uce) | ★52 | "Custom Elements via µhtml" |
| [dom-augmentor](https://github.com/WebReflection/dom-augmentor)| ★49 | "augmentor with DOM auto-hooked useEffect" |
| [hookedElements](https://github.com/WebReflection/hooked-elements) | ★26 | "wickedElements + augmentor" |

Heresy is still the choice if you want custom elements, hooks, JSX-like tagged template literals, and optional SSR. It looks and handles much the same as Preact+HTM. However there are about a dozen libraries here and one of them is sure to be exactly what you are looking for.

## Choice
- React - If you want a conventional development experience.
- Heresy (+ siblings) - If you want to walk on the wild side.
- Preact+HTM - if you want a compromise between the two.

I choose Preact+HTM in order to have a lightweight environment that can leverage many of the tools built for React. I also plan on giving Heresy (or sibling) a try once I have sorted out which one(s) to use.

[Next> Platform / Visual Design](PlatformVisualDesign.md#design)