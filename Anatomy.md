# Anatomy of a Web Application
A full web development environment might have many moving parts. Here are mamy of them.

## Platform
The technology and structure of the application.

| Aspect | Description |
| ------ | ----------- |
| [Team Dogma](PlatformDogma.md) | Things that should not matter - but do |
| [IDE](PlatformIDE.md) | The Integrated Development Environment used to write code  |
| [Repository](PlatformRepository.md) | A service to store and version code |
| [Language](PlatformLanguage.md) | What version of javascript to use |
| [Rendering Engine](PlatformRendering.md) | Render web page with data |
| [Visual Design](PlatformVisualDesign.md#design) | Styling of controls |
| [Widget Catalog](PlatformVisualDesign.md#catalog) | Library and showcase for controls |
| [Widget Structure](PlatformVisualDesign.md#structure) | Handling of complex control hierarchies |
| [Build Tools](PlatformBuild.md)| How to build your system. |


## Quality
Writing an application that works quickly and correctly.

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
| SSR | Server Side Rendering |


## Services
Creating an awesome back end server.

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
| Rate Limiting | Prevents server from being overwhelmed |
| Analytics | Determine who is using the site and how? |
| SEO | Search Engine Optimizations |


## Deployment
Packaging and hosting the application

| Aspect | Description |
| ------ | ----------- |
| Container | Packages the parts of the system |
| Orchestration | Coordinate containers |
| Server | The server that runs it all |

[Next> Platform / Team Dogma](PlatformDogma.md)