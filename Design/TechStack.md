# Technology Stack
At this point, we have selected PWA as our preferred approach. Depending on scale, there are a few stacks that can be used. I will list what I know in increasing capability. The names used here are my own.

---
## No Server
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
This is a simple web server that only serves html files and other resources. An example of this is [Servor](https://github.com/lukejacksonn/servor) which does nothing else but serves files to a local browser.

The served page might be very complex. It might connect to back-end services, use external libraries and have complex processing happening on the browser. All the while, the server has nothing to do but wait for file requests. While the web page is free to use back-end services, code on the browser is not secure. This can limit what is possible with a static server.

This approach works best for simple web sites that do not need much security. Many web development tools have one of these available to host the web page as it is being written.

---
## JamStack
[JamStack](https://jamstack.org/) refers to an architecture where pre-rendered content is served from a static server or [CDN](https://en.wikipedia.org/wiki/Content_delivery_network). Because this requires almost no server, it is a great solution for web sites that do not change often. Hosting is fast, cheap/free and reliable. Often the content is generated using [markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) or [MDX](https://mdxjs.com/). This lets the author generate nice looking content and mix in application logic if needed.

Security is enforced by the author needing to log into the host system to make changes. The generated site is public and cannot be changed by anybody reading the site.

A list of tools can be found [here](https://www.staticgen.com/). Some are shown below. 

Stars updated on 2020.07.20.

| Product | Stars | Description |
| ------- | -----:| ----------- |
| [Gatsby](https://github.com/gatsbyjs/gatsby) | ★45.9k | "Host at Scale for Pennies. Gatsby sites don’t require servers so you can host your entire site on a CDN for a fraction of the cost of a server-rendered site. Many Gatsby sites can be hosted entirely free on services like GitHub Pages and Netlify. Load Data From anywhere. Gatsby pulls in data from any data source, whether it’s Markdown files, a headless CMS like Contentful or WordPress, or a REST or GraphQL API. Use source plugins to load your data, then develop using Gatsby’s uniform GraphQL interface." |
| [Hugo](https://github.com/gohugoio/hugo) | ★45.6k | "Hugo is a static HTML and CSS website generator written in Go. It is optimized for speed, ease of use, and configurability. Hugo takes a directory with content and templates and renders them into a full HTML website. Hugo relies on Markdown files with front matter for metadata, and you can run Hugo from any directory. This works well for shared hosts and other systems where you don’t have a privileged account." |
| [Jeckyl](https://github.com/jekyll/jekyll) | ★40.9k | "Think of it like a file-based CMS, without all the complexity. Jekyll takes your content, renders Markdown and Liquid templates, and spits out a complete, static website. Jekyll is the engine behind GitHub Pages, which you can use to host sites right from your GitHub repositories." (By Github) |
| [React Static](https://github.com/react-static/react-static/tree/master/) | ★8.8k | "A progressive static site is a website where every statically exported HTML page is an entry point to a fully-featured automatically-code-split React application. Just like a normal static site, static progressive websites are capable of loading initial landing pages very quickly, but then extend the user experience by transforming invisibly into a single-page React application." |
| [RedwoodJS](https://github.com/redwoodjs/redwood) | ★4.2k alpha | "Redwood is an opinionated, full-stack, serverless web application framework that will allow you to build and deploy JAMstack applications with ease. Imagine a React frontend, statically delivered by CDN, that talks via GraphQL to your backend running on AWS Lambdas around the world, all deployable with just a git push—that's Redwood." (By Github) |
| [Unpoly](https://github.com/unpoly/unpoly) | ★613 | Not really a JAMStack. Unobtrusive JavaScript framework for server-side applications. It makes standard round-trip web sites look like SSR PWA. |

This approach works best for sites where a single author changes simple content from time to time. This could be a blog, portfolio or catalog.

---
## Classic Server
These are old-style sites where the server generates a new page for each interaction with the user. The most popular of these is [LAMP](https://blog.heroix.com/blog/monitoring-the-lamp-stack-using-longitude) - an acronym for Linux + Apache + MySQL + PHP (or Perl). Most web sites in the wild use this sort of structure, so term LAMP often refers to this family of technologies.

A classic server typically will run PHP, Java, C# or even Visual Basic. It will connect with a back end database, usually SQL. It will contain a templating engine of some sort (e.g., ASP, JSP) that intermixes data and html. A typical interaction with run as follows:

1. A browser requests a URL from the server
   - Security is handled by the server.
   - REST query may be contained in the request URL. 
   - Form data may be contained in the action attribute of the request.
2. The server interprets this request
	- data is updated to the database if needed.
	- data is fetched from the database if needed.
3. The server generates a new web page with requested data.
4. The server sends the web page to the browser as a response.

Typically there is no need for javascript on the browser. The context (state / session) are maintained by the server. Because this approach has been around for a long time, there are a lot of products that support it.

This approach works best for small, low volume sites for which cheap hosting might be important. Often the software uses preconfigured templates that make a site easy to set up.

---
## Modern Server
A modern server can serve web pages or data. The most popular one is MEAN: MongoDB + Express + Angular + Node.js. These differ from a classic server in that:
- the browser can request a web page but also data, streams, etc.
- the server can push data to the browser
- screen updates can be handled on the browser
- heavy reliance on javascript on the browser
- server is often assembled using code and libraries
- server is often written in Nodejs

While a PWA can be served by any means, it can request a lot of data, dynamic updates and make calls to services. This works best with a modern server.

## 💗Industrial Server
These are just Modern Servers designed to handle insane loads safely and securely. I use this term because they are built differently than a typical nodejs server. These are most often assembled from large prefabricated pieces of stand-alone software written in a performant language like Go. They can be built into containers like Docker, and connected together using a something like Docker-Compose, Docker Swarm or Kubernetics. They use a service-based architecture that can be spread out over many servers. These can be self-built and hosted, or they can be rented as cloud services. Ideally you can do both.

These need special consideration and are discussed at length later in this document. 



# Holotypes
In the article [Application Holotypes: A Guide to Architecture Decisions](https://jasonformat.com/application-holotypes/), Jason Miller describes the main categories of web applications and their overall architecture. This can inform our choice of tools, or at least get us thinking about the type of application we are writing. Spoiler: they are all PWA.

[Down> Design / Technology / Mdx](./Technology/Mdx.md)<br>
[Next> Design / Team Dogma](TeamDogma.md)