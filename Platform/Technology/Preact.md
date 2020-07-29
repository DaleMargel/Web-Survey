
# Preact ecosystem
I am really tending to favour Preact over React. A small Preact application can weigh in under 20k, while the same React application can be 50x as big. Here is some interesting stuff

| Name | Stars | Description |
| ---- | -----:| ----------- |
| [React/Webpack](https://stackoverflow.com/questions/36609910/react-without-webpack) | | Stack overflow question about using React without Webpack. The JSX needs WP, but compiling ES6+ to ES5- is just plain silly IMO. The article contains some good links. |
| [Create Preact App](https://github.com/alexkuz/create-preact-app) | ★67 | Create Preact apps with no build configuration. |
| [New in Preact X](https://blog.logrocket.com/whats-new-in-preact-x/) | | An overview of the new features in Preact X (Dec 2019) |
| [Awesome Preact](https://github.com/preactjs/awesome-preact) | ★413 | A master list of the preact ecosystem |
| [Microbundle](https://github.com/developit/microbundle)💗 | ★4.7k |  Zero-configuration bundler for tiny modules written by Jason Miller (preact,htm) and seems to like modern js. Used to create Preact. **Also flagged under packagers** |
| [Goober](https://github.com/cristianbote/goober) | ★1.2k | a less than 1KB tadacss-in-js alternative with a familiar API. Written as a lighter variety to styled-components(16k) or emotion(11k). Seems to prefer preact, but will work with others.
| [enzyme](https://github.com/enzymejs/enzyme/) | 18.7k | React testing framework that is also recommended by preact documentation. It works directly with screen components so it could be classified as UI test or E2E depending on the setup. |


# React or Preact
**TLDR;**
- Preact+Htm seems to give the best options. We can switch to React+Htm if Preact does not work out.

React targets ES5 (2009) using Babel and Webpack. **Yuck**. Some writers agree that this is silly. On [Dont Build that App!](https://formidable.com/blog/2019/no-build-step/) (Apr 2019), the author says that it is no longer necessary to go previous to ES6 / ES2015. He says that all modern browsers support ES6/2015. Don't worry about the ones that do not. He created [es-react](https://github.com/lukejacksonn/es-react) which is React with string template literals instead of JSX. It needs no webpack or babel and imposes a 50k overhead. I have already tried this library and I like it. The big problem is: can I use this with external libraries?

Another article [Minimal React](https://shinglyu.com/web/2018/02/08/minimal-react-js-without-a-build-step-updated.html) (Feb 2018) describes how to set up React with JSX but otherwise minimum use of babel and no use of webpack. It should be compatible with external libraries and might be the way to go. Even the official [React documentation](https://reactjs.org/docs/react-without-jsx.html) say that you do not need to use JSX, which just compiles down to `React.createElement(...)`

- [React without WebPack](https://stackoverflow.com/questions/36609910/react-without-webpack) Stack overflow answers, mostly to use babel to handle the JSX.
- [unpkg](https://unpkg.com/browse/@material-ui/core@4.9.3/) contains client accessible material design widgets. The problem here is that the client must dowload a lot of extra stuff that they will not need. Perhaps babel is needed for the JSX and web pack is needed to lighten the payload. Still ...

| Package | Stars | Description |
| ------- | -----:| ----------- |
| [React](https://github.com/facebook/react)  | ★146.0k | A declarative, efficient, and flexible JavaScript library for building user interfaces. <br>**SUMMARY:** The normal use depends on a complex build system and creates ugly 100M+ bloat. This was ok in 2010, but not now. |
| [Preact](https://github.com/preactjs/preact)💗 | ★25.8k | Fast 3kB React alternative with the same modern API. Components & Virtual DOM. Not as popular as React but far superior. |
| [SnowPack](https://github.com/pikapkg/snowpack) | ★6.7k | Build web applications with less tooling and 10x faster iteration. No bundler required. Basically it is a bundler that only runs when libraries change. |
| [Htm](https://github.com/developit/htm)💗 | ★5.7k | JSX alternative using standard tagged templates, with compiler support. Translates STL to `createElement`. No transpilier is necessary. Works with React or Preact and with Babel compiler (for optimization). There is also a pre-built [Preact+Htm](https://unpkg.com/htm/preact/standalone.module.js) npm that I tried and it works well. |
| [ESReact](https://github.com/lukejacksonn/es-react)💗 | ★124 | Builds on `Htm` but supplies a rebuilt React system using Htm that is available from a CDN https://unpkg.com/es-react. Because it is react, the size is larger than Preact, but compatibility will no doubt be better. Note that in order to use React directly as ESM, we cannot use Webpack, which forces the author to adapt `HTM` |
| [Heresy](https://github.com/WebReflection/heresy)💗 | ★204| Don't simulate the DOM. Be the DOM. React-like Custom Elements via the V1 API built-in extends. <br>**SUMMARY:** This is the best one, but I think this is ahead of its time. Sad. |

[Up > Platform / Rendering](../Rendering.md)