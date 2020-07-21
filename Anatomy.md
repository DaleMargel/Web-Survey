# Anatomy of a Web Application
A full web development environment and application have many moving parts. To some degree, all of these items should be decided - even if the choice is to ignore it.


## [Coder Religion](Religion.md)
Things that should not matter but do.

| Aspect | Description |
| ------ | ----------- |
| [Setting](Religion.md#setting) | Where you do the work |
| [OS](Religion.md#os) | Development operating system |
| [Code Standards](Religion.md#code-standards) | Placement of brackets, capitalization, etc. |
| [Tabs or Spaces](Religion.md#tabs-or-spaces) | Use of Tabs or Spaces |
| [Legacy Support](Religion.md#legacy-support) | Do we support obsolete browsers? |


## Platform
The technology and structure of the application.

| Aspect | Description |
| ------ | ----------- |
| [IDE](IDE.md) | The Integrated Development Environment used to write code  |
| [Repository](Repository.md) | A service to store and version code |
| [Language](Language.md) | What version of javascript to use |
| [Templating](Templating.md) | Render web page with data |
| [Design](VisualDesign#design) | Styling of controls |
| [Catalog](VisualDesign#catalog) | Library and showcase for controls |
| [Structure](VisualDesign#structure) | Handling of complex control hierarchies |


## Quality
Writing an application that works correctly and quickly.

| Aspect | Description |
| ------ | ----------- |
| Lint | Check code for structural bugs |
| Unit Test | Test code functions |
| Integration Test | Test interaction between components |
| Code Coverage | Make sure that everything is tested |
| End-to-End Test | Test whole application |
| SPA Compliance | Test that application supports SPA |
| Code Size | Track code size during development |
| Profile | Look for slow parts of application |
| Legacy Support | What do we support and how? |
| SSR | Server Side Rendering creates pages on server for extra speed |


## Services
Things that you need to interact with the real world.

| Aspect | Description |
| ------ | ----------- |
| Interface | How does the application talk to server? |
| Database | Stores data |
| Reverse Proxy | A server that serves other servers |
| Authentication | Ensure a user is who they say they are |
| External Login | Authentication from other web sites |
| Authorization | Allow varied access to system |
| Secure Socket | Support https |
| CORS | Allow access to other domains |
| Logger | Record errors for future analysis |
| Log Browser | Analyse logs |
| Load Balancer | Distributes requests among servers |
| Rate Limiting | Prevents server from being overwhelmed by requests |
| Analytics | Determine who is using the site and how? |
| SEO | Search Engine Optimizations lets Google properly index the site |


## Deployment
Packaging and hosting the application

| Aspect | Description |
| ------ | ----------- |
| Container | Packages the parts of the system |
| Orchestration | Coordinate containers |
| Server | The server that runs it all |

## [Next> Code Religion](Religion.md)