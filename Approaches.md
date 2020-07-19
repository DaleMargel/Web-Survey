# Web Approaches
To this point, we are dealing with a PWA web application. Depending on scale, there are a few approaches that can be used.

---
## Minimal
The most minimal web page I have encountered so far was listed in [PC World](https://www.pcworld.com/article/2360940/turn-any-browser-tab-into-a-basic-text-editor.html). Paste the following into your browser URL field and you will get a nice editor.

```html
data:text/html, <body contenteditable style="font: 2rem/1.5 monospace;max-width:60rem;margin:0 auto;padding:4rem;">
```
Your changes can be saved from the browser to a local file. Any tags with `contenteditible` attributes will have their changes stored intact. In Chrome this is `menu -> More tools -> Save page as...` (or Ctrl+s). In FireFox it is `menu -> Save page as...` (or Ctrl+s). Next time you open this file, it will display your changes.

This approach is used by [TiddlyWiki](https://tiddlywiki.com/) (also [here](https://github.com/Jermolene/TiddlyWiki5)). It does not need a server, but can make use of one if served from it.

Use this approach when you need a simple / personal application without a web server. Beware that the changes must be saved and that this cam feel a bit awkward on most browsers.

---
## Static
This is an html file served from a web site. The web page may have links to other pages. While this might look primitive, this **and all of the other approaches** may connect to back end servers, libraries and display sophisticated logic. A PWA can be served in this way.

This approach works best for sites that change rarely or not at all (although the data can).

---
## JamStack
[JamStack](https://jamstack.org/) refers to an architecture where pre-rendered content is served from a static server or [CDN](https://en.wikipedia.org/wiki/Content_delivery_network). Because this requires almost no server, it is a great solution for web sites that do not change often. Hosting is fast, cheap/free and reliable. Often the content is generated using [markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) or [MDX](https://mdxjs.com/). This lets the author generate nice looking content and mix in application logic if needed.

A list of tools can be found [here](https://www.staticgen.com/). This approach works best for sites that change from time to time - like a blog.

---
## Lamp Stack
These are Linux + Apache + MySQL + PHP (or Perl) based servers. These are considered "old style" web sites that work as follows:
1. A request is made to the web site server
   - REST query may be in the request URL. 
   - Form data may be in the action attribute of the request.
2. The server interprets this request and fetches the appropriate data from the SQL database.
3. The server uses a template to generate a web page.
4. The server sends the web page to the browser.

The main feature of this are that a round trip to the server must be made for each web page update. Typically there is no need for javascript on the browser.

This approach works best for ... legacy sites that wish to remain legacy. That is, although I have worked on many of these types of sites, I never liked this approach. Better options now exist.

---
## 💗Web Application
This is a web page that can be served by any of the means mentioned above. Once in play, the web page responds to the user actions directly and updates itself as needed. It can connect to a back end server to request data and dynamically update as the data changes.

Unlike other types of web pages, these will depend heavily on javascript executing on the browser. This makes them vulnerable to old browsers (i.e., IE) that do not support modern javascript. Also beware that code running on the browser is not secure.  

This approach works best for modern-style applications that will play nicely with Desktop and Mobile browsers.