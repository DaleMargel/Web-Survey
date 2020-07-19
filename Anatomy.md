# Anatomy of a Web Application
A full web development environment and application have many moving parts. To some degree, all of these items should be decided - even if the choice is not to support it.

## Platform

| Aspect | Description |
| ------ | ----------- |
| IDE | The Integrated Development Environment used to write code and orchestrate builds.  |
| Repository | A service to store and version code. |
| Language | What version of javascript to use |
| Templating | Render web page with data |
| Design | Styling of controls |
| Catalog | Library and showcase of components |
| Structure | Handling of complex control hierarchies |

## Quality

| Aspect | Description |
| ------ | ----------- |
| Lint | Check code for structural bugs |
| Unit Test | Test code functions |
| Integration test | Test connections between components |
| Code Coverage | Make sure that everything is tested |
| End-to-End test | Test whole application |
| SPA Compliance | Test that application supports SPA |
| Code Size | Track code size during development |
| Performance | Look for slow parts of application |
| Legacy Support | What do we support and how? |

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
| Log Browser | Searches, displays and correlates logs |
| Load Balancer | Distributes requests among servers |
| Rate Limiting | Prevents server from being overwhelmed by requests |
| Analytics | Determine who is using your site and how? |

## Deployment

| Aspect | Description |
| ------ | ----------- |
| Container | Packages the parts of the system |
| Orchestration | Coordinate containers |
| Server | The server that runs it all |

