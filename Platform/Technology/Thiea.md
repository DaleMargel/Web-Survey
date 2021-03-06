# The Thiea ecosystem
While searching for IDE's I came across **Thiea** and found it very interesting. While this is not what we are looking for, I think it can be useful enough to note here.

| Product | Stars | Description |
| ------- | -----:| ----------- |
| [Eclipse Theia](https://theia-ide.org/) | ★7.9k new | Eclipse Theia is a framework for building web-based IDEs and Tools (as opposed to VSCode which assumes you are writing code). The project has been an Eclipse open source project since 2018. Theia reuses quite a few technologies and concepts from VS Code, but it supports online deployment as well as a desktop deployment via electron right from its beginning. Driven by [SAP, RedHat, ARM, Google and others]. [Good Article here about release on 2020.03.31](https://www.globenewswire.com/news-release/2020/03/31/2009010/0/en/The-Eclipse-Foundation-Releases-Eclipse-Theia-1-0-a-True-Open-Source-Alternative-to-Visual-Studio-Code.html).<br> To run > `docker run -p 3000:3000 -v "$(pwd):/home/project:cached" theiaide/theia` when the dust settles, open the browser to http://0.0.0.0:3000/ |
| [Theia GLSP](https://www.eclipse.org/glsp/) | ★13 new | This is the Theia [Graphical Language Server Platform] that allows users to build graphical (visio-like) applications. It is based on Strotty but adheres to a format that can be supported by a Language Server. This allows the graphical language to have syntax rules, tool-tips, etc that any textual language already enjoys. |
| [Theia Strotty](https://github.com/theia-ide/sprotty) | ★142 | Diagramming on Theia. [Article here](https://www.typefox.io/blog/sprotty-a-web-based-diagramming-framework). This is a lower level API based on SVG on which GLSP is based. |
| [Theia Gitpod](https://www.gitpod.io/) | | `FREEMIUM` Used by Theia - Gitpod launches ready-to-code dev environments for your GitHub or GitLab project with a single click. The cost is free for limited use, but quickly climbs to $25/month for unfettered hosted use. |

[Up> Platform / Repository](../Repository.md)
