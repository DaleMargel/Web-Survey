# Team Dogma
This section should be tongue-in-cheek except that people actually argue about these things. At the risk of starting a war, let's dive in.

---
## HTML Header
What to put in the HTML header?

This should be simple and minimal, but it is not. Vendors impose header tags and the web standards keep changing. The solution is messy at best. 

Stars updated on 2020.07.20.

| Source | Stars | Description |
| ------ | -----:| ----------- |
| [HTML5 boilerplate](https://github.com/h5bp/html5-boilerplate)💗 | ★46.4k | "The web’s most popular front-end template. HTML5 Boilerplate helps you build fast, robust, and adaptable web apps or sites. Kick-start your project with the combined knowledge and effort of 100s of developers, all in one little package." |
| [HTML Shell](http://htmlshell.com/) | | A live web page generator. Elegant but basic. |

A statement on the complexity of web development is that the HTML5 Boilerplate has over 250 contributers and has been in flux for the past 10 years. This is just a landing page! Should it really be this complicated?

---
## Code Standards
Pick one.

No seriously, some people feel that the placement of braces is a big issue. Most languages have a culture and a preferred style of code. Most tools can format the code to any standard you might want.

Newer languages are very expressive and making code readable can be difficult. In these cases the community evolves sensible ways to make code easier to read.

So.. pick one well-worn standard and go with it.

---
## Tabs or Spaces

Really?? 

If there is a big tab key on my keyboard, I am probably going to use it. 

Any worthwhile code editor editor goes to great lengths to render this moot. I prefer to use tabs as tabs, and spaces as spaces.

- Tabs are for absolute positioning and can be adjusted.
- Spaces are for relative positioning of one character.
- Tabs can always align variable fonts, spaces cannot.
- Spaces render consistently across fixed width fonts, tabs might not.

If consistent text rendering is important, use spaces and a fixed width font. Otherwise, pick what ever makes the most sense and stick with it. Don't mix the two approaches.

One exception is Python, which seems to have control issues:
- Indentation must be 4 spaces (no tabs)
- Lines cannot exceed 79 characters
- Other strange indentation and line termination rules

Fortunately most serious compilers don't care about such trivial things as line length or use of whitespace. I prefer it that way too.

---
## Legacy Support
Do we support obsolete browsers like IE?

While many marketing departments and managers might want to support all browsers, they are often unaware of the cost of doing so. As of mid 2020, writing software using standard conventions can reach [almost 98% of browsers](https://caniuse.com/#feat=es6). Writing hacky code to reach the rest will catch a [further 1% to 2%](https://caniuse.com/#feat=es5) but it will take a lot more work and the results will be a disappointment.

The music industry has ceased supporting 8-tracks a long time ago. Movies are no longer released on VHS. Nobody bothers with CRT displays nor backing up data to tape cartriges or CD ROM. We should not use nor support dead technology. As a developer, [just say NO!](https://death-to-ie11.com/) - if you can.

---
## Big Project Syndrome
Is the project really a big project? 

Any small project can become a big project if it is treated as such. With a big project comes more overhead: more management, more developers, more code, more expense and a more likely failure.

Why do we do this? There are a lot of reasons: perverse incentives, cargo cult and herd mentality are a few. There are many good writers that have explored this at depth.

How to avoid this? Pick the simplest technology that will work - but leaves room for expansion. Not everything needs to be written in Angular on high-end distributed cloud service. As a developer, become familiar with a few approaches. That way you can make informed choices and save a lot of effort, cost and gnashing of teeth.

[Next> Design / Anatomy of a Web Application](Anatomy.md)