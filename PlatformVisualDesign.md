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

Standard CSS libraries are very common. A web search will uncover a great number of these. Here are a few of the more interesting ones. Some of the Design Systems in the next section support CSS too.

CSS libraries
- only style built-in controls (and custom elements),
- might supply much more CSS than you will use.

Stars updated 2020.07.23

| Package | Stars | Description |
| ------- | -----:| ----------- |
| [Bootstrap](https://github.com/twbs/bootstrap) | ★143k | Home: [web site](https://getbootstrap.com/)<br>Styling: Very standard looking (as it is the standard)<br>"The most popular HTML, CSS, and JavaScript framework for developing responsive, mobile first projects on the web." |
| [Normalize](http://necolas.github.io/normalize.css/) | ★39.8k | This sets the web browser to reasonable and consistent defaults. |
| [Material Components Web](https://github.com/material-components/material-components-web) | ★14.7k | Styling: Distinctive google style<br>"Material Components for the web helps developers execute Material Design. ... these components enable a reliable development workflow to build beautiful and functional web projects." / Material Components for the Web is the web portion of Material.io. It ia available via CDN, see [Getting Started](https://github.com/material-components/material-components-web/blob/master/docs/getting-started.md) |
| [Tachyons](https://github.com/tachyons-css/tachyons/) | ★9.7k | Styling: Standard looking<br>"Functional CSS for humans. Quickly build and design new UI without writing CSS." / Takes an inovative constraint-based approach for formatting elements. |
| [BuzzFeed Solid](https://solid.buzzfeed.com/) | | 82 controls. Nice and quite complete |
| [eBay Skin](https://ebay.github.io/skin/) | ★104 |  Looks very complete |
| [Aurora (Government of Canada)](https://design.gccollab.ca/) | | 19 controls. Looks good, simple and relatively small |
| [Nasa](https://github.com/bruffridge/nasawds) | ★24 | Looks a bit stark, but easy to use. |

## Design Systems
Design Systems are pre-packaged libraries of styled controls that can be used immediately with a specific development tool. Sometimes they are created by large companies for branding purposes.

The advantage of Design Systems over CSS libraries is that they can supply complex controls assembled from simpler ones. The drawback is that they can only be used with the frameworks they target - typically React.

A large list can be found at [Awesome Design Systems](https://github.com/alexpate/awesome-design-systems). Here are a few picks. The selection and comments are very subjective.

See Legend after table.<br>
Stars updated 2020.07.23

| Package | Stars | Description |
| ------- | -----:| ----------- |
| [Ant Design](https://github.com/ant-design/ant-design/) | ★61.9k | Home: [Ant Financial](https://ant.design/) (Alibaba?) <br>Controls: 62 formal / standard<br>Targets: React, Angular, Vue with Storybook, Sketch tooling |
| [Material.io](https://material.io/) | | This is the main site for Material Design stuff for Web, IoS, Android and Flutter. It mostly describes the specification. |
| [Material UI](https://github.com/mui-org/material-ui) | ★55.9k | Home: [Material UI](https://material-ui.com/)<br>Controls: 50 neutral / standard / look googly as expected<br>Targets: React, Preact, Gatsby, NextJs with themes |
| [Evergreen](https://github.com/segmentio/evergreen) | ★9.9k | Home: [Segment / Evergreen](https://evergreen.surge.sh/)<br>Controls: 20 formal / standard<br>Targets: React |
| [Primer](https://primer.style/components/) | ★9.4k | Home: [GitHub Primer](https://primer.style/)<br>Controls: 40 neutral / standard / definately GitHub<br>Targets: React, CSS<br>Note: This is a collection of 74 repositories that show just about everything you might want to know.  |
| [Carbon](https://github.com/carbon-design-system/carbon) | ★3.2k | Home: [IBM Carbon](https://www.carbondesignsystem.com/)<br>Controls: 34+ formal / advanced, charts<br>Targets: React, Angular, Vue,  Vanilla with sketch<br>Note: Variety of charts is amazing / needs sketch to extend |
| [rebass](https://github.com/rebassjs/rebass)💗 | ★6.7k | Home: [rebass](https://rebassjs.org/)<br>Controls: 16 technical / standard<br>Targets: React<br>Note: A CSS-in-JS framework that provides a good set of controls. React primitive UI components built with [Styled System](https://styled-system.com/) and can use [ThemeUI](https://theme-ui.com/) supplies wonderful set up for adding your own |
| [Grommet](https://github.com/grommet/grommet) | ★6.5k | Home: [Grommet](https://v2.grommet.io/) (Hewlett Packard?)<br>Controls: 49 technical / advanced, charts, markdown / with attitude<br>Targets: React with Sketch, Figma, Storybook, others<br>Note: accessiblity, theming, editors provided out of the box. |
| [Theme UI](https://github.com/system-ui/theme-ui) | ★2.8k | Home: [Theme UI](https://theme-ui.com/)<br>Components: 35 neutral / standard+markdown(MDX)<br>Targets: React, Gatsby<br>Note: A CSS-in-JS framework that provides a good set of controls. Theme UI combines several libraries together to form a mini-framework for styling applications.  It is built with: [emotions](https://emotion.sh/docs/introduction), [MDX](https://mdxjs.com/) and [styled systems](https://styled-system.com/) but also provides a bunch of components out of the box. |
| [Elastic UI](https://github.com/elastic/eui) | ★2.1k | Home: [Elastic UI](https://elastic.github.io/eui/#/)<br>Controls: 77 technical / standard, charts / crisp look<br>Targets: React, CSS<br>Conventional but crisp, insanely good charts!  |
| [Zendesk Garden](https://github.com/zendeskgarden) | ★774 | Home: [Home Site](https://garden.zendesk.com/)<br>Controls: 21 neutral / standard<br>Targets: React, CSS |
| [Pivotal UI](https://github.com/pivotal-cf/pivotal-ui) | ★631 | Home: [Pivotal UI](https://styleguide.pivotal.io/)<br>Controls 38 neutral / standard<br>Targets: React, CSS with Figma |
| [Preact Material Components](https://github.com/prateekbh/preact-material-components) | ★561 | Home: [Material Preact](https://material.preactjs.com/)<br>Targets: Preact<br>Note: Thin wrapper around [Material Components Web](https://github.com/material-components/material-components-web) targeting preact. |
| [BackPack](https://github.com/skyscanner/backpack) | ★359 | Home: [Skyscanner Backpack](https://backpack.github.io/)<br>Controls: 67  technical / standard / bold appearance looks great!<br>Targets: React(?), CSS, React Native, Android, iOS with Sketch |
| [Aragon UI](https://github.com/aragon/aragon-ui/) | ★210 | Home: [Aragon UI](https://ui.aragon.org/modal/)<br>Controls 57 formal / standard, charts<br>Targets: React |
| [Pluralsight](https://github.com/pluralsight/design-system) | ★185 | Home: [Pluralsignt](https://design-system.pluralsight.com/)<br>Controls: 43 technical / advanced / looks very crisp<br>Target: React<br>Note: components look really good! |
| [Balena](https://github.com/balena-io-modules/rendition) | ★134 | Controls: 48 neutral / standard, markdown / similar to Material Design<br>Targets: React with Storybook<br>Note: Excellent design, based on react, recompose, styled-components, and styled-systems. The widgets look a bit like material, but different enough to know that you are not using it |

Tip: code coloring can be done by [Prism](https://prismjs.com/)

### Legend

Tone: (subjective)
- formal : looks like a sheet of paper, "whiteish"
- business : looks like site for a big company
- neutral : looks like a regular website
- technical : nerdy with lots of graphs and stuff

Functionality:
- standard : the standard set of controls
- advanced : has controls that are uncommon
- charts : supports charts and graphs
- markdown : supports a markdown

--------------------
## CSS in JS
These are mostly framework-agnostic frameworks for injecting CSS into javascript. They do not supply any styles, just the means to create them. Many of the Design Systems use one of these as the underlying styling engine.

See https://styled-system.com/ecosystem for good overview<br>
Stars updated 2020.07.24

| Product | Stars | Description |
| ------- | -----:| ----------- |
| [Styled Components](https://github.com/styled-components/styled-components)💗 | ★30.3k | Home: [Styled Components](https://styled-components.com/)<br>Approach: Write `style` attribute<br>"Utilising tagged template literals (a recent addition to JavaScript) and the power of CSS, styled-components allows you to write actual CSS code to style of your components." / A bit React-centric, but can be used on other framework with a bit of effort. I did not see any handling of media queries. Note that DiegoHaz seems to like this library. |
| [emotion](https://github.com/emotion-js/emotion) | ★11.2k | Home: [emotion](https://emotion.sh/docs/introduction)<br>Approach: Write `style` attribute<br>Emotion is a CSS-in-JS library used to write css styles into a tag using javascript" / Looks similar to styled components but perhaps a bit more complicated |
| [styled system](https://github.com/styled-system/styled-system)💗 | ★6.0k | Home: [Styled System](https://styled-system.com/)<br>Approach: constraint-based system (a bit like Tachyons)<br>"Styled System lets you quickly build custom UI components with constraint-based style props based on scales defined in your theme." / Nice composition system handles resizing for you. Framework agnostic! |
| [JSS](https://github.com/cssinjs/jss) | ★5.8k | Approach: JS styles and React-callable method to compose+style components<br>"SS is framework agnostic .. which allows you to use JavaScript to describe styles in a declarative, conflict-free and reusable way. It can compile in the browser, server-side or at build time in Node." / No build pipeline. |
| [jsxstyle](https://github.com/jsxstyle/jsxstyle) | ★1.9k | Approach: Write custom attributes, which are added to `style` by framework<br>"jsxstyle is an inline style system for React and Preact. Inline styles on these components are converted to CSS rules and added to the document right as they’re needed." |
| [NyanCSS](https://github.com/nyancss/nyancss)💗 | ★529 | Approach: Use CSS selector naming convention to inject styles<br>"Nyan CSS lets you write plain CSS while reaping benefits of CSS-in-JS." / Supports Html, Preact, Vue and React(?). It uses webpack to tweak the css code and appears to be mostly framework agnostic. |

---

# Catalog and tools
Library and showcase for controls

There are a set of tools used to help style web sites
- Library and Showcase : [StoryBook](https://storybook.js.org/)
- Screen design tool using styled components : 
  - [Sketch](https://www.sketch.com/) : Mac only, paid
  - [Figma](https://www.figma.com/) : paid, but with community edition 
  - [others](https://www.slant.co/options/5279/alternatives/~sketch-alternatives)

---
# Component Structure
Handling of complex control hierarchies

As your project gets bigger, managing the components and all of their subcomponents and dependencies becomes a chore. This might help.

| Product | Stars | Description |
| ------- | -----:| ----------- |
| [Arc](https://github.com/diegohaz/arc)💗 | ★2.5k | React starter kit based on the [Atomic Design methodology](https://bradfrost.com/blog/post/atomic-web-design/) - see also [DiegoHaz](DiegoHaz.md) library |

[Next> Platform / Build Tools](PlatformBuild.md)