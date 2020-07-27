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
| [Elm](https://github.com/elm)⚑ |  | Home: [Elm](https://elm-lang.org/)<br>Compiles code written in Elm (a functional language) to vanilla javascript. Because it is written as it's own language, it has many innovative ideas that are impossible in a javascript-like language. Otherwise, it is similar to Svelte, but has a strange syntax. |
| [Heresy](https://github.com/WebReflection/heresy)💗 | ★218| "React-like Custom Elements via the V1 API built-in extends. Also available for SSR." |

## Vue
By github stars, this is the most popular framework. It was released in 2014 as a lighter alternative to Angular. I must admit that I have no experience with it. It uses a combination of annotated html and declarative javascript to bind data to the web page. I understand that it is very popular in China, but not as much in North America.

## React
By media reports, this is the most popular framework by far. It is certainly the best supported. It has been around since 2013.

React is powered by JSX, an XML-like extension to javascript. This allows javascript and pseudo-html to be intermixed with wild abandon. As hugely popular as it is, it does have a few quirks:

- It uses JSX, which requires a build step to convert to javascript.
- It seems to prefer targeting ES5.
- It uses virtual DOM difference to optimise updates.
- It tends to change its favoured approach from time to time.
- It has its own events, not those of the browser.
- It can generates large run-time bundles by default.

The currently favoured approach is hooks. This is a brilliant way to decouple the user interface from the data. React offers a number of hooks but there are some [third party libraries](https://github.com/streamich/react-use) that take it to an extreme.

Technically speaking, React does not need to use JSX and therefore does not need to be "built". During build, JSX is comverted to `React.createElement()`. If you are willing to call this directly (or some shorter alias like hyperscript), the code will run directly without the need for building. JSX just makes it easier, and if you are using a transpiler, there is no reason not to use it.

## Angular
This was released in 2010 but underwent a major change in 2016. While not as popular as React and Vue, it is popular with big companies and therefore there are a lot of jobs for Angular programmers. It presents a more structured MVC programming model that has a higher learning curve than the others. It also uses Typescript and needs to be compiled to javascript. It generates the largest bundles of the tools listed here.

## Svelte
This framework seems to come up a lot. It was released in 2016. It reads annotated xhtml with javascript and compiles it into a focused light-weight vanilla js web application. I have not used this, but it looks promising.

## Preact
Preact is a lightweight and faster version of React. It has a light-weight virtual DOM, it uses the browser events and it removes those lesser-used features that take up space. Because of this, it imposes a 3kb overhead compared to React's 136kb. Preact also has a React-compatibility library that implements the missing React features if you need them.

Preact makes no secret about using hyperscript under the hood to compose the page. it even exports the `h()` function so you can use it directly. It also gives you the option of using a built tool to support JSX if you want to use Preact like it was React.

If Preact is combined with [HTM](https://github.com/developit/htm), interesting things happen. Htm uses tagged template literals (TTL) in much the same way as JSX, but because TTL is part of javascript the code may run directly in the brower. No compile step is needed. This is why I like it so much. It is likely that something similar exists in React, but HTM was written by the same author as Preact, so you can be more comfortable that it will work.

## Polymer
Web Components were a proposed standard to allow a developer to define their own HTML tags with custom behaviour and scoped styles. Polymer chose to define these components as web fragments containing embedded javascript. For this all to work it needed:

- HTML Imports : loading html like a script
- Custom Elements : ability to define custom tags and behaviours
- Shadow DOM : ability to access hidden DOM inside of tags
- HTML Templates : ability to define tags outside of DOM

Polymer depended heavily on HTML Imports so when it failed to become a W3C standard Polymer was stopped in its tracks. The work around was to import javascript files containing HTML rather than HTML files containing javascript. The Google team started writing [lit-html](https://lit-html.polymer-project.org/) to do this.

Polymer seemed to lose a lot of momentum while it was writing lit-html. Many good libraries already existed for this and I don't know why the Polymer team did not just adopt one and move on.

> Ironically, if you squint at lit-html (or heresy) it looks similar to React. These vendors are trying to solve the same problem: filling an annotated template with data.

## Elm
Elm works similar to Svelte, but it uses a custom language with a lot of innovative features. Because it is unfamilar looking, it has a steeper learning curve and is not as popular as svelte.


## Heresy
Polymer used to be my preferred approach until Web Components were killed by W3C. The Polymer team started working with an aternative, lit-html, but I found that [HyperHTML](https://viperhtml.js.org/hyper.html) was already a more capable and mature replacement - so I moved over to [WebReflection](https://github.com/WebReflection) and never looked back.

The since then, Andrea created a succession of libraries to explore possible solutions. I tried [Heresy](https://github.com/WebReflection/heresy) and liked it. It is the best choice if you want custom elements, hooks, JSX-like tagged template literals, and optional SSR. It looks and handles much the same as Preact+HTM or React but uses a technology more similar to Polymer (custom elements), but is lighter weight (no shadow dom).

Heresy uses custom elements v1 which are widely supported. It even runs on problematic IE9, IE10, IE11, Safari and Web Kit browsers with a small polyfill. The library is light (26.9kb/min) and fast. Tags created by Heresy can be treated as regular HTML tags.

If you want a different approach there are also a dozen other libraries listed. One of them is sure to be exactly what you are looking for. See the [WebReflection](../People/WebReflection.md) section of this document for details.

## Weapon of Choice
My take:
- React - If you want a conventional development experience.
- Heresy (or sibling) - If you want to walk on the wild side.
- Preact+HTM - if you want a compromise between the two.

I choose Preact+HTM in order to have a lightweight environment that can (in theory) leverage many of the tools built for React. I also plan on giving Heresy (or sibling) another try once I have sorted out which one(s) to use.

# Rendering

HTML has a few advantages compared to javascript
- it is much smaller than the equivalent javascript
- html web sites display more quickly than javascripted ones
- it can be read by crawlers and help out SEO ratings

At the same time, javascript makes it easier to constuct large hierarchies of responsive controls.

How do we get the best of both worlds?

## Server Rendering
Much of this depends on what is being rendered where.

| Approach | Description |
| -------- | ----------- |
| Classic | Static HTML pages are sent from the server to the client. This is the fastest solution for static content. |
| CSR | Client Side Rendering : the server sends javascript to the client which is then used to render a web page. This is responsive but it can be big and slow. |
| SSR | Server Side Rendering : the server renders the javascript into HTML then sends the HTML to the client for rendering. This can be much faster than CSR if the content is relatively static. |
| Mixed | The landing page is SSR but the other pages are CSR. This gives a fast start up without too much loss of reactivity |
| PH | Partial Hydration : the server renders some javascript as HTML but writes others into scripts tags to be run on the client. Any page may have a combination of these. This is the best solution and lets the developer decide how best to render. |

[Partial Hydration](https://medium.com/@luke_schmuke/how-we-achieved-the-best-web-performance-with-partial-hydration-20fab9c808d5) best if you can do it. While relatively new but I expect it to become a preferred technique over the next few years. See also [this article](https://markus.oberlehner.net/blog/building-partially-hydrated-progressively-enhanced-static-websites-with-isomorphic-preact-and-eleventy/#demo-and-full-code). An added advantage of PH is the potential for supporting all browsers. If a feature fails it falls back to SSR which should at least render the component.


## DOM Diffing

Updating the DOM is time-consuming so many frameworks keep track of what has changed and only update that part of the screen. The main difference between React, Preact and Heresy is the approach to tracking these changes.

- React maintains a virtual DOM, a sort of copy of how the screen should look. It compares the virtual DOM with the current one to determine what has changed. This can take time and a lot of memory.

- Preact works in a similar manner as React, but the code was written to be fast and light [(see video)](https://www.youtube.com/watch?v=LY6y3HbDVmg&feature=youtu.be). 

- Heresy takes advantage of tagged template literals. The only DOM elements that can change are those bits represented by the "holes". This lets heresy make the DOM diffing extremely light and blazingly fast without the need for a virtual DOM.

I like the Heresy approach, but Preact still has the smallest size.

## Managing Control Hierarchies
As applications get bigger so do the number of controls. Managing these can become quite difficult.

One approach is [Atomic Design](https://atomicdesign.bradfrost.com/) which is an idea (and Book) by Brad Frost. It recommends breaking up the contols folder into 5 folders - based on level in hierarchy. 

1. basic styled html controls. 
2. aggregates above to have a purpose (e.g. search, login).
3. aggregates above to a unit of work (e.g. header, catalog, photos).
4. aggregates above into page layouts for different screens sizes.
5. aggregates above into specific page (e.g. landing, settings, payment).

Stars updated 2020.07.24

| Product | Stars | Description |
| ------- | -----:| ----------- |
| [Arc](https://github.com/diegohaz/arc)💗 | ★2.5k | React starter kit based on the [Atomic Design methodology](https://bradfrost.com/blog/post/atomic-web-design/) - see also [DiegoHaz](DiegoHaz.md) library |



[Next> Platform / Visual Design](VisualDesign.md#design)