# Approach
How to build an application that runs everywhere?

There are a lot of interesting technologies out there. How do we narrow the list? The first cut is the approach that the tool takes toward targeting a platform. In reality there are only a few approaches.

| Approach | Description |
| -------- | ----------- |
| Native | These are tools that target one platform. The application must be re-written mostly from scratch for each platform. The resulting application is usually fast and capable, but it takes a lot of work and expertise to write. |
| Multi Target | These are languages that can target a large number of platforms. Typically these do not support web, or they don't support it very well. |
| Web Hybrid | These are web pages with a web browser and web server bolted on to them. They look good and run anywhere, but they are very big. |
| [PWA](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps)💗 | A design pattern that allows web pages to be run as regular applications using the local web browser as a run time agent. These tend to be small and run on any platform that has an evergreen web browser. |

### The Central Problem
In this document, the term "cross-platform" to means that the same code can be used to write applications for Desktop, Mobile and Web. This is more difficult than it seems. Each target (Desktop, Mobile, Web) has a different way of generating output. We want a tool hides these differences and presents a unified programming model to the developer. 

Desktop and Mobile are similar enough that universal tools exist. The problem is with web. It is very different from Desktop and Mobile making it hard to bridge.

There are two directions one can take:

- Write a Desktop / Mobile application also that compiles to Web page.
- Write a Web page that can be packaged into a native app.

Multi-target platforms take the first approach; Web hybrid take the second.

## Native
This is the best way to write an application for a single platform. It is the most expensive way to write an applicaton for many platforms. If we want to target Web, Linux, Windows, Mac, Android, and iOS we need to write the application 6 times. All of these would be quite different and need a lot of detailed knowledge about the platform and the tools used. This is not feasible.  

## Multi-Target
There are languages that, usually via [LLVM](https://llvm.org/), can target a large number of platforms. Many of these have tools that enable running on multiple platforms using the same code. Often these tools do not support Web, or support it badly.

Also on the radar is Web Assembly (WASM). This is low level code that can run on a web browser, but cannot (yet) directly write to the screen.

| Product | Description |
| ------- | ----------- |
| [Flutter](https://flutter.dev/)⚑ | Uses the Dart language and targets Desktop, Mobile and Web. Developers seem to like it and it is rising quickly in popularity. / I have not used it yet, but from what I see, it is worth a try.  |
| [Haxe](https://haxe.org/) | This started out as a 'flash' alternative, but has evolved well beyond it. It can compile to a range of languages: JavaScript, C++, C#, Java, Java(VM), Python, Lua, PHP, Flash, Neko(VM) and HashLink(VM). It can target any common platform. It supports Web through javascript, but not through a cross-platform API. |
| [Haxe/OpenFL](https://www.openfl.org/) | This is a cross-platform library, but it is intended for games. |
| [Haxe/Cocktail](https://github.com/silexlabs/Cocktail) | Implements HTML/CSS parts of a web browser as a DOM-style callable library. Calls to this library result in a widget being rendered natively. An identical call to the javascript library results in a widget being rendered to a browser. / This is truly a cross-platform library, and an amazing and ambitious project. Unfortunately it suffers from incomplete support of modern HTML5. I guess it was too ambitious! |
| [Xamarin](https://github.com/xamarin) | Targets Desktop, Mobile and WASM using C#. / No Web Support. |
| [Kotlin](https://kotlinlang.org/)⚑ | Targets Desktop, Mobile, Web (via javascript) and WASM. / I do not know how well it supports Web but intend to eventually have a look. |
| [Rust](https://www.rust-lang.org/)⚑ | A C++ replacement that compiles nicely to most native platforms and the preferred tool for WASM. It is intended for writing low level system code and handling large code bases. It has strict rules for sharing memory and can therefore ensure its integrity and deterministic life cycle. No GC needed. / I have not yet explored the ecosystem for cross-platform code generation, but it is likely that some exist.  |
| [Go](https://golang.org/)⚑ | A C++ replacement that runs on most platforms, but most especially servers. Go is a minimal language that handles fibers (small threads) really well. / As with Rust, I have not explored the ecosystem for cross-platform code generation, but it is likely that some exist. |

## Web Hybrid
These run web code in a native runtime, typically bolting a web server and browser on to the web page to make it look like an application. Most of these do not support all platforms (Desktop, Mobile, Web) or the resulting code can be very large and not work well on smaller mobile devices. See also [Awesome Desktop JS](https://github.com/styfle/awesome-desktop-js) that has some of these and many others.

| Product | Description |
| ------- | ----------- |
| [React / Native](https://reactnative.dev/) | Insanely popular ecosystem for Mobile or Web. / No Desktop support and Web applications can become very large |
| [NativeScript](https://nativescript.org/) | Accepts html-like/css/javascript code and renders it natively to Mobile platforms. / No Desktop. |
| [Capacitor](https://capacitorjs.com/) | "Capacitor turns any web app into a native app so you can run one app across iOS, Android, and the Web with the same code." / No Desktop. |
| [Ionic](https://ionicframework.com/) | "Ionic Framework is an open source mobile UI toolkit for building high quality, cross-platform native and web app experiences. Move faster with a single codebase, running everywhere." / No Desktop. |
| [Electron](https://www.electronjs.org/) | "Build cross-platform desktop apps with JavaScript, HTML, and CSS." / No Mobile |
| [NWJS](https://nwjs.io/) | "NW.js (previously known as node-webkit) lets you call all Node.js modules directly from DOM and enables a new way of writing applications with all Web technologies." / No Mobile |
| [PhoneGap](https://phonegap.com/) | "Adobe PhoneGap framework is an open source distribution of Cordova" / No Desktop |
| [Cordova](https://cordova.apache.org/) | "Mobile apps with HTML, CSS & JS. Target multiple platforms with one code base" / No Desktop |
| [Tauri](https://github.com/tauri-apps/tauri/) | "Tauri is a framework for building tiny, blazing fast binaries for all major desktop platforms. Developers can integrate any front-end framework that compiles to HTML, JS and CSS for building their user interface. The backend of the application is a rust-sourced binary with an API that the front-end can interact with." / All platforms, smaller runtimes. |



Extra points to NWJS for being really simple to use.


## Progressive Web Application (PWA)

A PWA is just a web page that uses a few conventions to allow the browser to handle it as an application. In other words, an installable web application. When not installed they are run as an ordinary web page.

Unlike classic web pages, these can depend heavily on javascript executing on the browser. They are also vulnerable to browsers that do not support modern web standards (i.e., IE, older Safari) - but gracefully degrade when used as such. Also beware that code running on the browser is not secure.  

Advantages:

- Treated as native application.
- Write once, run anywhere.
- Easy to find on web (web search).
- Quick and easy to install (click of a button).
- No App Stores to deal with.
- Updates are automatically applied.
- No need for a connected server.
- Small code size compared to other approaches.

Disadvantages:

- Rely on modern browser, but degrade gracefully.
- Not as fast or capable as native code.
- Web look & feel rather than native.
- Code on client is not secure.
- The web is really not that simple ...

## My Choice..
PWA's have the most potential.

[Next> Design / Technology Stack](TechStack.md)