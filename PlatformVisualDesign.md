# Platform Visual Design
How to make your web page look good.

Designing and building a beautiful web page is somewhat of an art. Expressing the design in CSS is more difficult. Having it look nice in all screen sizes and orientations is almost impossible. As a result, most developers (including myself) write ugly web pages.

Fortunately we can just grab a pre-existing design and start developing. The bigger question is how? There are a few ways to do this.

- **CSS Libraries** : the most direct way to apply styling
- **CSS-in-JS** : provide a low level, framework agnostic technique to inject styles into code.
- **Design Systems** : portfolios of controls and styles written for a specific framework or environment.
- **Style Systems** : perform complex high level platform agnostic styling

## The Problem with Styling

CSS was created for a designer mindset and not developers. Most developers have a love/hate relationship with it. While it is powerful, it is also awkward to use, especially with modern web applications.

- CSS is big, really big. Read the specs to find out how big.
- CSS is not scoped, so any rule applies to the whole site.
- CSS is overloaded: it handles styling, layout, animation, effects, screen sizing and more.
- CSS rules have complex priorities. !important
- CSS contains many ugly bits. Clearfix anybody?
- CSS contains ad-hoc hacks to get around obscure problems.
- CSS is often inconsistent and with side-effects.
- CSS file size can exceed the rest of the application!
- CSS can have inconsistent browser support, see [QuirksMode](https://www.quirksmode.org/compatibility.html).
- Browsers default styling is not standardized, see [Normalize](http://necolas.github.io/normalize.css/).

Over the years many work-arounds have been created to get around these problems: [LESS](http://lesscss.org/), [SASS](https://sass-lang.com/), [Stylus](https://stylus-lang.com/) to name a few. They work to a point, but they do not solve all of these problems. 

Much to their credit, the CSS2 and CSS3 standards do much to get around many of the original rough spots. Using, for example, **FlexBox** and **Grid** lets the designer/developer avoid a whole lot of pain that would be inflicted by older techniques. The trick is knowing a lot of recipies.

With the growing popularity of javascript-centric web frameworks (e.g. React), **CSS-in-JS** approaches are getting a lot of traction. These are styles written in javascript rather than css. While they seem disliked by many, they do get around some of the issues.

The solution? CSS is here to stay, so adopt a CSS (or CSS-in-JS) library and learn to live with it.

---------------------
## CSS Libraries

Standard CSS libraries are very common. A web search will uncover a huge number of these. Here are a few of the more interesting ones.

Stars udated 2020.07.23

| Package | Stars | Description |
| ------- | -----:| ----------- |
| [Bootstrap](https://github.com/twbs/bootstrap) | ★143k | "The most popular HTML, CSS, and JavaScript framework for developing responsive, mobile first projects on the web." / The main [web site](https://getbootstrap.com/) supplies all of the options in easy downloadable formats. |
| [Normalize](http://necolas.github.io/normalize.css/) | ★39.8k | This sets the web browser to reasonable and consistent defaults. |
| [Material Components Web](https://github.com/material-components/material-components-web) | ★14.7k | "Material Components for the web helps developers execute Material Design. ... these components enable a reliable development workflow to build beautiful and functional web projects." / Material Components for the Web is the web portion of Material.io. It ia available via CDN, see [Getting Started](https://github.com/material-components/material-components-web/blob/master/docs/getting-started.md) |
| [Tachyons](https://github.com/tachyons-css/tachyons/) | ★9.7k | "Functional CSS for humans. Quickly build and design new UI without writing CSS." / This file takes an interesting approach for formatting elements but has little in the way of advanced controls. |
| [Primer](https://github.com/primer) | ★9.4k | "Primer was created for GitHub by GitHub. We love it so much, we chose to open-source it to allow the community to design and build their own projects with Primer." / [Home Site](https://primer.style/css/) 45 components, CSS and React. Looks like its GitHub alright. |
| [BuzzFeed Solid](https://solid.buzzfeed.com/) | | 82 controls. Nice and quite complete (82.5kb minified) |
| [eBay Skin](https://ebay.github.io/skin/) | ★104 |  Looks very complete (146kb) |
| [Aurora (Government of Canada)](https://design.gccollab.ca/) | | 19 controls. Looks good, simple and relatively small (202kb) |
| [Nasa](https://github.com/bruffridge/nasawds) | ★24 | Looks a bit stark, but easy to use. |

## Design Systems
Design Systems are pre-packaged libraries of styled controls that can be immediately used in a specific development tool. Most typically they target React and often in TypeScript. Sometimes they are created by large companies for branding purposes.

A large list can be found at [Awesome Design Systems](https://github.com/alexpate/awesome-design-systems). Here are a few picks, with a slight bias for Preact.

Stars udated 2020.07.23<br>
See Legend after table.

| Package | Stars | Description |
| ------- | -----:| ----------- |
| [Ant Design](https://github.com/ant-design/ant-design/) | ★61.9k | Home: [Ant Financial](https://ant.design/) (Alibaba?) <br>Controls: 62 formal / standard<br>Targets: React, Angular, Vue with Storybook, Sketch tooling |
| [Material.io](https://material.io/) | | This is the main site for Material Design stuff for Web, IoS, Android and Flutter. It mostly describes the specification. |
| [Material UI](https://github.com/mui-org/material-ui) | ★55.9k | Home: [Material UI](https://material-ui.com/)<br>Controls: 50 normal / standard / look googly as expected<br>Targets: React, Preact, Gatsby, NextJs with themes |
| [Evergreen](https://github.com/segmentio/evergreen) | ★9.9k | Home: [Segment / Evergreen](https://evergreen.surge.sh/)<br>Controls: 20 formal / standard<br>Targets: React |
| [Primer](https://primer.style/components/) | ★9.4k | Home: [GitHub Primer](https://primer.style/)<br>Controls: 40 normal / standard / definately GitHub<br>Targets: React, CSS<br>Note: This is a collection of 74 repositories that show just about everything you might want to know.  |
| [Carbon](https://github.com/carbon-design-system/carbon) | ★3.2k | Home: [IBM Carbon](https://www.carbondesignsystem.com/)<br>Controls: 34+ formal / advanced+charts<br>Targets: React, Angular, Vue,  Vanilla with sketch<br>Note: Variety of charts is amazing / needs sketch to extend |
| [Grommet](https://github.com/grommet/grommet) | ★6.5k | Home: [Grommet](https://v2.grommet.io/) (Hewlett Packard?)<br>Controls: 49 technical / advanced, charts, markdown / with attitude<br>Targets: React with Sketch, Figma, Storybook, others<br>Note: accessiblity, theming, editors provided out of the box. |
| [Elastic UI](https://github.com/elastic/eui) | ★2.1k | Home: [Elastic UI](https://elastic.github.io/eui/#/)<br>Controls: 77 technical / standard, charts / crisp look<br>Targets: React, CSS<br>Conventional but crisp, insanely good charts!  |
| [Zendesk Garden](https://github.com/zendeskgarden) | ★774 | Home: [Home Site](https://garden.zendesk.com/)<br>Controls: 21 normal / standard<br>Targets: React, CSS |
| [Pivotal UI](https://github.com/pivotal-cf/pivotal-ui) | ★631 | Home: [Pivotal UI](https://styleguide.pivotal.io/)<br>Controls 38 normal / standard<br>Targets: React, CSS with Figma |
| [Preact Material Components](https://github.com/prateekbh/preact-material-components) | ★561 | Home: [Material Preact](https://material.preactjs.com/)<br>Targets: Preact<br>Note: Thin wrapper around [Material Components Web](https://github.com/material-components/material-components-web) targeting preact. |
| [BackPack](https://github.com/skyscanner/backpack) | ★359 | Home: [Skyscanner Backpack](https://backpack.github.io/)<br>Controls: 67  technical / standard / bold appearance looks great!<br>Targets: React(?), CSS, React Native, Android, iOS with Sketch |
| [Aragon UI](https://github.com/aragon/aragon-ui/) | ★210 | Home: [Aragon UI](https://ui.aragon.org/modal/)<br>Controls 57 formal / standard+charts<br>Targets: React |
| [Pluralsight](https://github.com/pluralsight/design-system) | ★185 | Home: [Pluralsignt](https://design-system.pluralsight.com/)<br>Controls: 43 technical / advanced / lookd very crisp<br>Target: React<br>Note: components look really good! |
| [Balena](https://github.com/balena-io-modules/rendition) | ★134 | Controls: 48 normal / standard, markdown / similar to Material Design<br>Targets: React with Storybook<br>Note: Excellent design, based on react, recompose, styled-components, and styled-systems. The widgets look a bit like material, but different enough to know that you are not using it |

Tip: code coloring can be done by [Prism](https://prismjs.com/)

### Legend

Tone: (subjective)
- formal : looks like a sheet of paper, "whiteish"
- business : looks like site for a big company
- normal : looks like a regular website, kind of neutral tone
- technical : nerdy with lots of graphs and stuff

Classes:
- standard : the standard set of controls
- advanced : has controls that are uncommon
- charts : supports charts and graphs
- markdown : supports a markdown

---------------------
** WARNING: information past this point is still being edited **


--------------------
## CSS in JS
These are react-based components that provide styling in javascript. These are often used to provide themes to the styled-systems in next section.

| Product | Stars | Description |
| ------- | -----:| ----------- |
| [styled components](https://styled-components.com/)💗 | ★28.7k | Creates tags with embedded CSS as tagged template literals. You can then use those tags in react, or wherever you want. Also available as a CDN (32.5k). Babel is not necessary but is recommended forSSR, minification and a nicer debugging experience. Under the hood, it creates React components with css inside. Example: `const Title = styled.h1'color:green';` Non-react components can be used with some additional hassle. <br>**VERDICT:** Good, syntax is nice, but library it is react-centric. I did not see any handling of media queries. Note that DiegoHaz seems to like this library. He has a styled-themes which is quite nice. |
| [emotion](https://emotion.sh/docs/introduction) | ★10.4k | Emotion  is used for writing css styles within the tag using javascript, e.g., `<div css={css'background-color: hotpink;'}>`. <br>**VERDICT:** same as sytled components, but looks more complicated |
| [glamorous](https://github.com/paypal/glamorous) | ★3.7k | **DEPRECATED:** lipstick Maintainable CSS with React -> Use emotion instead |
| [jsxstyle](https://github.com/jsxstyle/jsxstyle) | ★1.9k | jsxstyle is an inline style system for React and Preact. Inline styles on these components are converted to CSS rules and added to the document right as they’re needed. |
| [NyanCSS](https://github.com/nyancss/nyancss)💗 | ★525 | Write plain CSS while reaping benefits of CSS-in-JS. Allows you to write CSS for (P)React tags using in a simple manner and have those available to (P)React components as simple flags or enumeration. It uses Webpack to tweak the code. |
| [Arc](https://github.com/diegohaz/arc)💗 | ★2.5k | React starter kit based on the Atomic Design methodology - see also DiegoHaz section |

## Styling Web Pages
As an alternative to design systems, there are lighter weight alternatives that let you render your own style more easily using css-in-js. 

TLDR;
- [styled system](https://styled-system.com/) is framework agnostic and is used by others
- [emotion](https://emotion.sh/docs/introduction) supplies styles and is used by others
- [rebass](https://rebassjs.org/) is like "styled components" with batteries included
- see https://styled-system.com/ecosystem for good overview




## Styled Systems
These are more complex assemblies to provide theming. Some are react-centric, others not.

TLDR;
- Use Design Systems instead: try these when I get more experience.

| Product | Stars | Description |
| ------- | -----:| ----------- |
| [rebass](https://rebassjs.org/)💗 | ★6.4k | React primitive UI components built with [Styled System](https://styled-system.com/) and can use [ThemeUI](https://theme-ui.com/). <br>**GOOD:** supplies some controls based on ThemeUI which in itself is a great library. |
| [styled system](https://styled-system.com/)💗 | ★5.6k | Styled System lets you quickly build custom UI components with constraint-based style props based on scales defined in your theme. <br>**GREAT:** Nice constraint-based composition system handles resizing for you. Framework agnostic! |
| [ThemeUI](https://theme-ui.com/) | ★2.1k | Theme UI combines several libraries together to form a mini-framework for styling applications. It is built with: [emotions](https://emotion.sh/docs/introduction), [MDX](https://mdxjs.com/) and [styled systems](https://styled-system.com/) but also provides a bunch of components out of the box! |

---------------------

## Catalog and tools
Library and showcase for controls

## Structure
Handling of complex control hierarchies

[Next> Platform / Build Tools](PlatformBuild.md)