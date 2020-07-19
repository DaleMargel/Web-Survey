# Anatomy of a Web Application
A full web development environment and application have many moving parts. To some degree, all of these items should be decided - even if the choice is to ignore it.

## Platform

| Aspect | Description |
| ------ | ----------- |
| IDE | The Integrated Development Environment used to write code  |
| Repository | A service to store and version code |
| Language | What version of javascript to use |
| Templating | Render web page with data |
| Design | Styling of controls |
| Catalog | Library and showcase for controls |
| Structure | Handling of complex control hierarchies |

## Quality

| Aspect | Description |
| ------ | ----------- |
| Lint | Check code for structural bugs |
| Unit Test | Test code functions |
| Integration test | Test interaction between components |
| Code Coverage | Make sure that everything is tested |
| End-to-End test | Test whole application |
| SPA Compliance | Test that application supports SPA |
| Code Size | Track code size during development |
| Profile | Look for slow parts of application |
| Legacy Support | What do we support and how? |
| SEO | Search Engine Optimizations lets Google properly index the site |
| SSR | Server Side Rendering renders the first page on the server for extra startup speed |

## Services

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

## Deployment

| Aspect | Description |
| ------ | ----------- |
| Container | Packages the parts of the system |
| Orchestration | Coordinate containers |
| Server | The server that runs it all |

