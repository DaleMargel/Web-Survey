# Team Dogma
This section should be tongue-in-cheek except that people actually argue about these things. At the risk of starting a war, let's dive in.

## Landing Page
What is needed on a landing page? This should be simple and minimal, but it is not.

Stars updated on 2020.07.20.

| Source | Stars | Description |
| ------ | -----:| ----------- |
| [HTML5 boilerplate](https://github.com/h5bp/html5-boilerplate)💗 | ★46.4k | "The web’s most popular front-end template. HTML5 Boilerplate helps you build fast, robust, and adaptable web apps or sites. Kick-start your project with the combined knowledge and effort of 100s of developers, all in one little package." |
| [HTML Shell](http://htmlshell.com/) | | A live web page generator. Elegant and basic. |

A statement on the complexity of web development is that the HTML5 Boilerplate has over 250 contributers and has been in development for 10 years. This is just a landing page! Should it really be this complicated?

---
## Setting
Picture an awesome place to work.

Perhaps it is an image of a young coder with a hipster beard packing a MacBook Pro and writing brilliant code from a coffee shop in Kathmandu while travelling the world. It could be some beautiful people huddled around a large table joyfully socializing while writing code with their sylishly small laptops. 

I suspect the truth is quite the opposite. The most productive working spaces for developers tend not look like a poster for WeWork.

For serious coding you need a big screen (maybe two or three) and a comfortable, quiet, ergonomically sound workspace. Working from home is good unless you are distractible or have young kids. I consider a private office with a door and an outside view ideal.

In most environments you will probably be stuck in a cubicle (while management and corporate get the offices). This can be made tolerable with a set of earphones to cancel out the noise. Take short hourly breaks, standing by a window to get a bit of sun and looking at distant objects to relieve eye strain. 

The worst place to work is at a crowded table. I would rather work in a coffee shop shop in Kathmandu.

---
## OS

What operating system is used on the destop / laptop for development? 

| Aspect | Description |
| ------ | ----------- |
| MacOS | I have no experience with Apple products. Until recently Apple had a reputation for not supporting advanced HTML features (e.g. Custom Elements). Do you really want to do web development on a machine with a crippled web browser?  |
| Windows | Unless you are using Visual Studio / C#, Windows seems to make development more difficult in a million small ways. |
| Linux💗 | I honestly love using MX Linux (a Debian derivative) for development. It is free and runs well on an 8 year old recycled laptop. If your server also runs Linux, the experience is smooth and seamless. Just about any Linux will do. |

I guess it is really just a matter of taste.

---
## Code Standards
Pick one.

No seriously, some people feel that the placement of braces is a big issue. Generally speaking most languages have a culture and a preferred style of code. Most tools can format the code to any standard you might want.

Newer languages are very expressive and making code readable can be difficult. In these cases the community evolves sensible ways to make code easier to read.

So.. pick one standard and go with it.

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

The music industry has ceased supporting 8-tracks a long time ago. Movies are no longer released on VHS. Nobody bothers with CRT displays nor backing up data to tape cartriges or CD ROM's. We should not use nor support dead technology. As a developer, [just say NO!](https://death-to-ie11.com/) - if you can.

[Next> Platform / IDE](IDE.md)