# Platform Build Tools 
Sometimes you need to build your system. Here's how.

Hopefully I will not have to use one of these, but it might be hard not to. These are tools that compile javascript to javascript making some changes to it along the way. React does this to convert JSX to javascript and package libraries into a saner structure. I personally do not like the idea, but in a large project it might be a necessity. There is a great article [here](https://jasonformat.com/enabling-modern-js-on-npm/) that explains the whole situation and says: "the dependencies we install from npm are stuck in 2014" - and therefore we need to package things... The author thinks that the whole npm/package infrastructure is broken. He is also the author of preact and htm, so he seems to prefer things be lightweight. 

Stars updated on 2020.07.20.

| Product | Stars | Description |
| ------- | -----:| ----------- |
| [Webpack](https://github.com/webpack/webpack) | ★55.0k | "A bundler for javascript and friends. Packs many modules into a few bundled assets." |
| [Prettier](https://github.com/prettier/prettier) | ★37.2k | "Prettier is an opinionated code formatter. It enforces a consistent style by parsing your code and re-printing it with its own rules that take the maximum line length into account, wrapping code when necessary." |
| [Babel](https://github.com/babel/babel) | ★37.0k | "The compiler for writing next generation JavaScript." |
| [Rollup](https://github.com/rollup/rollup) | ★18.6k | "Rollup is a module bundler for JavaScript which compiles small pieces of code into something larger and more comple." |
| [Browserify](https://github.com/browserify/browserify) | ★13.3k | "Use a node-style require() to organize your browser code and load modules installed by npm." |
| [Rome](https://github.com/facebookexperimental/rome) ⚑ | ★9.4k new | "Rome is an **experimental** JavaScript toolchain. It includes a compiler, linter, formatter, bundler, testing framework and more. Rome was started by Sebastian McKenzie, the author of Babel and Yarn. Rather than assembling a build pipeline by passing source code through multiple disparate tools for various tasks, Rome performs all build and compile steps itself." |
| [Microbundle](https://github.com/developit/microbundle)💗 | ★5.0k |  Zero-configuration bundler for tiny modules written by Jason Miller (creator of preact and htm) and seems to like modern js. Used to create Preact |
| [Terser](https://github.com/terser/terser) | ★4.5k | "A JavaScript parser and mangler/compressor toolkit for ES6+." |
| [Zwitterion](https://github.com/lastmjs/zwitterion)💗 | ★489 | This is web dev server that lets you import anything to the browser: JavaScript ES2015+, TypeScript, JSON, JSX, TSX, AssemblyScript, Rust, C, C++, WebAssembly, and in the future anything that compiles to JavaScript or WebAssembly. Normally you have to run webpack to transpile these into something the browser understands. Zwitterion does the conversion automatically. To create a static build for production, run Zwitterion with the `--build-static` option. Under the hood it appears to use the `node.http` as the base server and calls webpack as needed. |
| [Preppy](https://github.com/sebastian-software/preppy) | ★22 | "A simple and lightweight tool for preparing the publish of NPM packages. Creates multiple output formats (ESM, CommonJS, UMD, ...)" |
