# Choices
There are a lot of interesting technologies out there. While this is not a comprehensive list, it covers the broader strokes.

## Achitecture
The basic approach of the tool is important.

| Approach | Description |
| -------- | ----------- |
| Native | These are tools that target one platform. The application must be re-written mostly from scratch for each platform. This does not align with our goals, so we shall skip it henceforth. |
| Multi Target | These are languages that can target a large number of platforms. Typically these do not support web, or they don't support it very well. |
| Web Hybrid | These are web pages with a web browser and web server bolted on to them. They look good and run anywhere, but they are very big. See: [Capacitor](https://capacitorjs.com/), [Ionic](https://ionicframework.com/), [Electron](https://www.electronjs.org/), [NWJS](https://nwjs.io/), [PhoneGap](https://phonegap.com/), [Cordova](https://cordova.apache.org/). Extra points to NWJS for being really simple to use. |
| 💗[PWA](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps) | A Progressive Web Application (PWA) is a design pattern that allows web pages to be run as regular applications using the local web browser as a run time agent. These tend to be small and run on any platform that has an evergreen web browser (which is most). |

## And the winner is...
For our needs, Progressive Web Applications (PWA) are the best approach. The advantages:

- They look and feel like an installed application.
- Write once, run anywhere.
- Easy to locate (web search) and install (click of a button).
- No App Stores to deal with.
- Updates are automatically applied.
- No need for a connected server.
- Small code size compared to other approaches.

## Special Mention / Frameworks
There are some frameworks that deserve mention. The issue with most of these is that they do not support all platforms (Desktop, Mobile, Web) or that the resulting code can be very large.

| Product | Description |
| ------- | ----------- |
| [React / Native](https://reactnative.dev/) | <p>Insanely popular ecosystem for Mobile / Web. No Desktop support and Web applications can become very large</p> |
| [NativeScript](https://nativescript.org/) | <p>Accepts html-like/css/javascript code and renders it natively to Mobile platforms. No Desktop support. </p> |
| [Flutter](https://flutter.dev/) | <p>Uses the Dart language and targets Desktop / Mobile / Web. Developers seem to like it and it is rising quickly in popularity. I have not used it yet, but from what I see, it is worth a try.</p>  |

## Special Mention / Languages
There are languages that, usually via [LLVM](https://llvm.org/), can target a large number of platforms. The issue with most of these is that the web display model (DOM) is quite different from native display models - making it difficult to bridge.

Also on the radar is Web Assembly (WASM). This is low level code that can run on a web browser. It cannot directly interact with the user interface (yet), but will become more important over time.

I use the term "cross-platform" to mean that the same code can be rendered native as well as on a web browser with little or no changes. Most of the languages below can render on a browser through javascript, but not in a cross-platform manner.

| Product | Description |
| ------- | ----------- |
| [Haxe](https://haxe.org/) | <p>This started out as a 'flash' alternative, but has evolved well beyond this. It can compile to a range of languages: JavaScript, C++, C#, Java, JVM, Python, Lua, PHP, Flash, Neko(VM) and HashLink(VM). It can target just about anything. It supports Web through javascript, but not through a cross-platform API.</p><p>There is an excellent haxe library [OpenFL](https://www.openfl.org/) that is cross-platform, but it is intended for games. Another library, [Cocktail](https://github.com/silexlabs/Cocktail) implements relevant html/css parts of a web browser. This is truly a cross-platform library, but suffers from incomplete support of modern HTML5.</p> |
| [Xamarin](https://github.com/xamarin) | <p>Targets Desktop / Mobile / WASM using C#. No Web Support.</p> |
| [Kotlin](https://kotlinlang.org/) | <p>Targets Desktop / Mobile / Web (via javascript) / WASM.</p> |
| [Rust](https://www.rust-lang.org/) | <p>A C++ replacement that compiles nicely to most native platforms and WASM. It is intended as a system language for large code bases.</p><p>I included this because it seems to be the preferred way to create high quality WASM</p>  |
| [Go](https://golang.org/) | <p>A C++ replacement that runs on most platforms, but most especially servers.<p>I included this because there is a large ecosystem of server-based technologies written in this language</p> |

## [Next> Approaches](Approaches)