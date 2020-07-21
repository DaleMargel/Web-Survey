# Technology Stack
At this point, we have selected PWA as our preferred approach. Depending on scale, there are a few stacks that can be used. I will list what I know in increasing capability. The names used here are my own.

---
## Minimal
Just to start the ball rolling...

The most minimal web page I have encountered so far was listed in [PC World](https://www.pcworld.com/article/2360940/turn-any-browser-tab-into-a-basic-text-editor.html). Paste the following into your browser URL field and you will get a nice editor.

```html
data:text/html, <body contenteditable style="font: 2rem/1.5 monospace;max-width:60rem;margin:0 auto;padding:4rem;">
```
Your changes can be saved from the browser to a local file. Any tags with `contenteditible` attributes will have their changes stored intact. In Chrome save using `menu -> More tools -> Save page as...` (or Ctrl+s). In FireFox use `menu -> Save page as...` (or Ctrl+s). Next time you open this file, it will display your changes.

This approach is used by [TiddlyWiki](https://tiddlywiki.com/) (also [here](https://github.com/Jermolene/TiddlyWiki5)). It does not need a server, but can make use of one if available.

This is of limited use but can be used when you need a simple / personal application without a web server. Beware that the changes must be saved and that this can feel a bit awkward on most browsers.

---
## Static Server
This is a simple web server that only serves html files and other resources. An example of this is [Servor](https://github.com/lukejacksonn/servor) which does nothing else but serves files to a browser.

The served page might be very complex. It might connect to back-end services, use external libraries and have complex processing happening on the browser. All the while, the server has nothing to do but wait for file requests. While the web page is free to use back-end services, code on the browser is not secure. This can limit what is possible with a static server.

This approach works best for simple web sites that do not need much security. Many web development tools have one of these available to view the web page as it is being written.

---
## JamStack
[JamStack](https://jamstack.org/) refers to an architecture where pre-rendered content is served from a static server or [CDN](https://en.wikipedia.org/wiki/Content_delivery_network). Because this requires almost no server, it is a great solution for web sites that do not change often. Hosting is fast, cheap/free and reliable. Often the content is generated using [markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) or [MDX](https://mdxjs.com/). This lets the author generate nice looking content and mix in application logic if needed.

Security is enforced by the author needing to log into the host system to make changes. The generated site is public and cannot be changed by anybody reading the site.

A list of tools can be found [here](https://www.staticgen.com/).

This approach works best for sites where a single author changes simple content from time to time. This could be a blog. portfolio or catalog.

---
## Classic Server
These are old-style sites where the server generates a new page for each interaction with the user. The most popular of these is [LAMP](https://blog.heroix.com/blog/monitoring-the-lamp-stack-using-longitude) - an acronym for Linux + Apache + MySQL + PHP (or Perl). Most web sites in the wild use this sort of structure, so term LAMP often refers to this family of technologies.

A classic server typically will run PHP, Java, C# or even Visual Basic. It will connect with a back end database, usually SQL. It will contain a templating engine of some sort that intermixes data and html. A typical interaction with run as follows:

1. A browser requests a URL from the server
   - Security is handled by the server.
   - REST query may be contained in the request URL. 
   - Form data may be contained in the action attribute of the request.
2. The server interprets this request
	- data is updated to the database if needed.
	- data is fetched from the database if needed.
3. The server generates a new web page with data.
4. The server sends the web page to the browser as a response.

Typically there is no need for javascript on the browser. The context (state / session) are maintained by the server. Because this approach has been around for a long time, there are a lot of products that support it.

This approach works best for small, low volume sites for which cheap hosting might be important. Often the software uses preconfigured templates that make a site easy to set up.

---
## 💗Modern Server
A modern server can serve web pages or data. The most popular one is MEAN: MongoDB + Express + Angular + Node.js. These differ from a classic server in that:
- the browser can request web pages or data
- the server can push data to the browser
- screen updates can be handled on the browser
- heavy reliance on javascript on the browser
- server is more configurable

While a PWA can be served by any means, it can request a lot of data, dynamic updates and make calls to services. This works best with a modern server.


[Next> Anatomy of a Web Application](Anatomy.md)