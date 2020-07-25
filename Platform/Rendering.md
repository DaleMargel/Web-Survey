# Platform Rendering Engine
How to convert your code to a web page.

This is a HUGE topic and there are a great number of products that do this. At it's core, most of these take an annotated html template and inject data into it. How this is done can vary widely. The short list below are the notable ones plus a few that I really like.

For a real-life comparisons of the various frameworks, look at [ToDo MVC](http://todomvc.com/). For even better PWA-specific comparisons look at [HackerNews PWA](https://hnpwa.com/). There are a lot of comparison sites for React, Vue, Angular. Here is [one of them](https://www.codeinwp.com/blog/angular-vs-vue-vs-react/).

Stars current as of 2020.07.22

| Product | Stars | Description |
| ------- | -----:| ----------- |
| [Vue](https://github.com/vuejs/vue) | ★168k | "a progressive framework for building user interfaces." |
| [React](https://github.com/facebook/react) | ★153k | "A declarative, efficient, and flexible JavaScript library for building user interfaces." |
| [Angular](https://github.com/angular/angular.js) | ★63.5k | "Angular is a development platform for building mobile and desktop web applications using TypeScript/JavaScript and other languages" |
| [Svelte](https://github.com/sveltejs/svelte)⚑  | ★35.6k | "a compiler that takes your declarative components and converts them into efficient JavaScript that surgically updates the DOM" |
| [Preact](https://github.com/preactjs/preact)💗 | ★26.7k | A lighweight version of React |
| [Polymer](https://github.com/Polymer/polymer) | ★21.4k| The most successful Web Component library (until it was killed by W3C) |
| [Elm](https://github.com/elm)⚑ | ★333 | Home: [Elm](https://elm-lang.org/)<br>Compiles code written in Elm (a functional language) to vanilla javascript. Because it is written as it's own language, it has many innovative ideas that are impossible in a javascript-like language. Otherwise, it is similar to Svelte, but a strange syntax. |
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
- It can generates large run-time bundles by default.

The currently favoured approach is hooks. This is a brilliant way to decouple the user interface from the data. React offers a number of hooks but there are some [third party libraries](https://github.com/streamich/react-use) that take it to an extreme.

## Angular
This was released in 2010 but underwent a major change in 2016. While not as popular as React and Vue, it is popular with big companies and therefore there are a lot of jobs for Angular programmers. It presents a more structured MVC programming model that has a higher learning curve than the others. It also uses Typescript and needs to be compiled to javascript. It generates the largest bundles of the tools listed here.

## Svelte
This framework seems to come up a lot. It was released in 2016. It reads annotated xhtml with javascript and compiles it into a focused light-weight vanilla js web application. I have not used this, but it looks promising.

## Elm
Elm works similar to Svelte, but it uses a custom language with a lot of innovative features. Because it is unfamilar looking, it has a steeper learning curve and is not as popular as svelte.

## Preact
Preact is a lightweight and faster version of React. It has a light-weight virtual DOM, it uses the browser events and it removes those lesser-used features that take up space. Because of this, it imposes a 3kb overhead compared to React's 136kb (minified). Preact also has a compatibility library that implements the missing React features if you need them.

If combined with [HTM](https://github.com/developit/htm) the code may run directly in the brower with no compile step. This is why I like it so much.

## Polymer
Web Components were a proposed standard to allow a developer to define their own HTML tags with custom behaviour and scoped styles. Polymer chose to define these components as web fragments containing embedded javascript. For this all to work it needed:

- HTML Imports : loading html like a script
- Custom Elements : ability to define custom tags and behaviours
- Shadow DOM : ability to access hidden DOM inside of tags
- HTML Templates : ability to define tags outside of DOM

Polymer depended heavily on HTML Imports so when it failed to become a W3C standard Polymer was stopped in its tracks. The work around was to import javascript files containing HTML rather than HTML files containing javascript. The Google team started writing [lit-html](https://lit-html.polymer-project.org/) to do this.

Polymer seemed to lose a lot of momentum while it was writing lit-html. Many good libraries already existed for this and I don't know why the Polymer team did not just adopt one and move on.

> Ironically, if you squint at lit-html (or heresy) it looks similar to React. These vendors are trying to solve the same problem: filling an annotated template with data.

## Heresy
Polymer used to be my preferred approach until Web Components were killed by W3C. The Polymer team started working with an aternative, lit-html, but I found that [HyperHTML](https://viperhtml.js.org/hyper.html) was already a more capable and mature replacement - so I moved over to [WebReflection](https://github.com/WebReflection) and never looked back.

The since then, Andrea created a succession of libraries to explore possible solutions. I tried [Heresy](https://github.com/WebReflection/heresy) and liked it. It is the best choice if you want custom elements, hooks, JSX-like tagged template literals, and optional SSR. It looks and handles much the same as Preact+HTM or React but uses a technology more similar to Polymer (custom elements), but is lighter weight (no shadow dom).

Heresy uses custom elements v1 which are widely supported. It even runs on problematic IE9, IE10, IE11, Safari and Web Kit browsers with a small polyfill. The library is light (26.9kb/min) and fast. Tags created by Heresy can be treated as regular HTML tags.

If you want a different approach there are also a dozen other libraries listed. One of them is sure to be exactly what you are looking for. See the [WebReflection](../People/WebReflection.md) section of this document for details.

## DOM Diffing

Updating the DOM is time-consuming so many frameworks keep track of what has changed and only update that part of the screen. The main difference between React, Preact and Heresy is the approach to tracking these changes.

- React maintains a virtual DOM, a sort of copy of how the screen should look. It compares the virtual DOM with the current one to determine what has changed. This can take time and a lot of memory.

- Preact works in a similar manner as React, but the code was written to be fast and light [(see video)](https://www.youtube.com/watch?v=LY6y3HbDVmg&feature=youtu.be). 

- Heresy takes advantage of tagged template literals. The only DOM elements that can change are those bits represented by the "holes". This lets heresy make the DOM diffing extremely light and blazingly fast without the need for a virtual DOM.

## The Future
Frameworks were invented to work around the limitations of older web browsers. With the capabilities of modern web, many have questioned whether we still need frameworks at all. 

React, Angular, Vue are all frameworks that in some way are solving yesterday's problems. They assist in creating proprietary components and must transform the code to do this. 

Polymer and Heresy are libraries and technically superior. They create components that are native to the web browser. The code does not need to be transformed. The library is only there to automate some of the boilerplate work and is not always needed.

Which approact wins? React, Angular, Vue has huge momentum and a lot of support / tooling. People test to stick with what they find familiar. My guess is that the React group will stay more popular for years to come.

## Weapon of Choice
- React - If you want a conventional development experience.
- Heresy (or sibling) - If you want to walk on the wild side.
- Preact+HTM - if you want a compromise between the two.

I choose Preact+HTM in order to have a lightweight environment that can (in theory) leverage many of the tools built for React. I also plan on giving Heresy (or sibling) another try once I have sorted out which one(s) to use.

[Next> Platform / Visual Design](VisualDesign.md#design)