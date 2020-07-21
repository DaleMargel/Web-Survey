# Team Dogma
This section should be tongue-in-cheek except that people actually argue about these things. At the risk of starting a war, let's dive in.

---
## Setting
A narrative out there is a young coder with a hipster beard porting a Mac laptop and writing brilliant code from a coffee shop in Katmandu while travelling the world. 

In another narrative, there are a bunch of beautiful people crowded around a large table writing code with their sylishly small laptops. An expresso machine adorns a shelf in the background.

I suspect the truth is quite opposite.

For most coding you need a big screen (maybe two or three) and a comfortable, quiet, ergonomically sound workspace. Working from home is good unless you are distractible or have young kids. I consider a private office with a door and an outside view ideal.

In most environments you are stuck in a cubicle (while management has the offices). These can be made tolerable with a set of earphones to cancel out the noise. Take short hourly breaks, standing by a window to get a bit of sun and looking at distant objects to relieve eye strain. 

The worst place to work is at a crowded table. I would rather work in a coffee shop shop in Katmandu.

---
## OS

What operating system is used on the destop / laptop for development? 

| Aspect | Description |
| ------ | ----------- |
| MacOS | I have no experience with Apple products (by choice). |
| Windows | Unless you are using Visual Studio / C#, Windows seems to make development more difficult in a million small ways. |
| 💗Linux | I honestly love using my MX Linux (a Debian derivative) for development. It is free and runs well on an 8 year old recycled laptop. If your server also runs Linux, the experience is smooth and seamless. |

I guess it is really just a matter of taste.

---
## Code Standards
Pick one.

No seriously, some people feel that the placement of brackets is a big issue. Generally speaking most languages have a culture and a preferred style of code. Most tools can format the code to any standard you might want.

Newer languages are very expressive and making code readable can be quite a challange. I find that the community tends to evolve reasonable conventions even in these cases.

I prefer classic [K&R](https://en.wikipedia.org/wiki/Indentation_style) style which seems to match the javascript conventions reasonably well.

---
## Tabs or Spaces

Really??

Any worthwhile code editor editor goes to great lengths to render this moot. I prefer to use tabs as tabs and spaces as spaces. If there is a big tab key on my keyboard, why should I not use it?

- Tabs are for absolute positioning and can be adjusted.
- Spaces are for relative positioning of one character.
- Tabs can always align variable fonts, spaces cannot.
- Spaces render consistently for fixed width fonts, tabs might not.

If consistent text rendering is important, use spaces and a fixed width font. Otherwise, use what ever makes the most sense.

One exception is Python, which seems to have control issues:
- Indentation must be 4 spaces (no tabs)
- Lines cannot exceed 79 characters
- Other strange indentation and line termination rules

Fortunately most serious compilers don't care about such trivial things as line length or use of whitespace. I prefer it that way too.

---
## Legacy Support
Do we support obsolete browsers like IE?

While many marketing departments and managers might want to support all browsers, they are often unaware of the cost of doing so. As of mid 2020, writing software using standard conventions can reach [almost 98% of browsers](https://caniuse.com/#feat=es6). Writing hacky code to reach the rest will catch a [further 1% to 2%](https://caniuse.com/#feat=es5) but it will take a lot more work and the results will be a disappointment.

The music industry has ceased supporting 8-tracks a long time ago. Movies are no longer released on VHS. Nobody bothers with CRT displays nor backing up their data to tape cartriges or CD ROM's. We should not use nor support dead technology. As a developer, [just say NO!](https://death-to-ie11.com/) - if you can.

[Next> Platform / IDE](PlatformIDE.md)