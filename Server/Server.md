# Server

## Server Interface
# REST
We need to interconvert between a back-end data store and code-accessible data. This is the central decision we have to make based on our needs - since some of these provide other services. What choices are there?

- Auto-mapping : **PostgREST** can directly query a Postgresql database out of the box.
- Rest-based: generate tables and data based on POST commands
- Declarative: uses a mapping between data and code
- Imperative: uses code to generate the query and package the results

I originally chose **PostgREST** but later changed my mind. While it supplies restful mappings right out of the box, this is not what I need. The actual rest->sql conversion is more complex than a simple 1:1 mapping. There is no simple way to express the business logic except to code it directly, and it will vary from one application to the next. PostgREST forces the developer to put the business logic into the database (yuck) and this code is not readily transported to another database. An ADMIN and ANONYMOUS user can request the same data but get wildly different results. It looks like manually coding the request handlers using an ORM is the best approach. **TypeORM** seems to be the best choice.

GraphQL is a more advanced REST. See [devathon blog](https://devathon.com/blog/graphql-vs-or-rest/) for a good writeup. for We will stick with REST for now. Below are some of the libraries to generate REST. I will not be using any of them as I think it best to write code to do this instead. See ORM discussion below.

| Product | Stars | Description |
| ------- | -----:| ----------- |
| [ReThink](https://rethinkdb.com/) | ★23.5k | **NB** This does not support REST, but I did not know where else to put it. RethinkDB a JSON database for the real-time web. RethinkDB can continuously push updated query results to applications in real-time. RethinkDB’s realtime push architecture dramatically reduces the time and effort necessary to build scalable realtime apps. |
| [Mongoose](https://github.com/Automattic/mongoose) | ★20.5k | This [article](https://www.toptal.com/nodejs/secure-rest-api-in-nodejs) outlines how to set up Node + Express + Mongo + REST. There is also [github](https://github.com/makinhs/rest-api-tutorial) code. The code is exceptionally well organized, but also, there is a lot of it since it is translating the REST in node.
| [PostgREST](https://github.com/PostgREST) | ★14.2k | PostgREST is an elegant REST to SQL converter that does all of the REST/SQL translation for you. While it has a lot of potential, it also requires a lot of configuration on the server. This makes it extremely secure, but requires that you write a lot of code in SQL which I find obnoxious. |
| Postgresql | | This [article](https://itnext.io/building-restful-api-with-node-js-express-js-and-postgresql-the-right-way-b2e718ad1c66) discusses setting up Node + Express + JWT + Postgresql. The [github](https://github.com/krofax/Transport-Booking-Backend-Api) is here. This code creates a set of controllers that have raw SQL generation. There is also some really good descriptions on how to run postman. |
| [Restify](https://github.com/restify/node-restify) | ★9.7k | restify is a framework, utilizing [connect](https://github.com/senchalabs/connect) style middleware for building REST APIs |
| [GraphQL](https://github.com/graphql/express-graphql) | ★5.2k | Creates GraphQL requests in Express |
| [restful mongoose](https://github.com/developit/restful-mongoose) | ★88 | Expose Mongoose models as RESTful Express resources. |
| [RAML](https://raml.org/) | | A specification for designing restful interfaces. The tools can be found [here](https://raml.org/projects#q:osprey) which seem to include everything you need to bootstrap your api (osprey, postman) |


## Database

# ORM's
This could be any number of possible back-ends.

**TLDR;**

Hard choice. I thought this over and decided that I really need to construct queries manually because there is a lot of business logic that needs to be handled. The same query from a ADMIN or ANONYMOUS may have dramatically different results. **PostgREST** forces you to put this logic into the database (yuck!). Automating this would force you to define it declaratively (also yuck). The easiest approach is just write the queries manually, but use a tool that supports this. **TypeORM** seems to be at the right level of abstraction and it supports most SQL databases as well as MongoDB. While TypeORM prefers typescript it can run off javascript if json schemas are manually added.

ORMS by popularity
| Name | Stars | Supports | Description |
| ---- | -----:| -------- | ----------- |
| [Sequelize](https://github.com/sequelize/sequelize) | ★21.3k | sql | with generator using [relay](https://github.com/mickhansen/graphql-sequelize), but GraphQL only and seems quite wordy. There are a lot of plugins, including graphical query builders ([sequelize-ui](https://github.com/tomjschuster/sequelize-ui)) create models from existing postgres ([ pg-generator](http://www.pg-generator.com/builtin-templates/sequelize/)), and many others. |
| [Mongoose](https://github.com/Automattic/mongoose) | ★20.4k | mongo only | |
| [TypeORM](https://typeorm.io/#/)💗 | ★17.9k | 9 sql + Mongo | DataMapper or ActiveRecord, nice query builder, integrates with [vesper](https://github.com/vesper-framework/vesper)★509 GraphQL builder that seems quite logical (though manual) but GraphQL only! For REST, use [routing-controller](https://github.com/typestack/routing-controllers)★2.4k. This is more manual but not bad. While it prefers typescript with annotations, it can be used with javascript provided [json schemas](https://github.com/typeorm/typeorm/tree/master/sample/sample24-schemas) are used.<br>**SUMMARY**: Use this one.  |
| [PostgREST](http://postgrest.org/en/stable/index.html) | ★14.1k | Postgres | Automatically converts between rest and sql on database. Fast and secure. All configuration is on database which can be a pain, but puts all the pain in one place and in one language (SQL). |
| [Loopback](https://loopback.io/) | ★13.0k | sql/nosql | can generate api, but TypeScript and looks complex |
| [Knex](https://github.com/knex/knex) | ★11.5k | sql | a lot of tools based on this. Basically a nice query builder. |
| [BookShelf](https://github.com/bookshelf/bookshelf) | ★5.8k | | similar to Sequelize, built on knex |
| [derby](https://github.com/derbyjs/derby/) | ★4.5k | ? | MVC framework making it easy to write realtime, collaborative applications. Looks complicated. |
| [JugglingDb](https://github.com/1602/jugglingdb) | ★2.0k | 2 sql/10 nsoql | Wide support, server+client, code model first |
| [compound](https://github.com/1602/compound) | ★1.6k | see JugglingDB | Web site in a box with REST generation, HTTPS, the works. Looks kind of complicated. See also RailwayJS which is much the same but less applicable. |
| [caminte](https://github.com/biggora/caminte) | ★1.1k | | a really good database ORM that supports anything. Has a generator called [caminte generator](https://github.com/biggora/caminte-generator)★8 - supports all databases, has rest query generator, based on CanintelJS ORM . Old, not popular but quite intriguing. | 
| [MikRORM](https://mikro-orm.io/) | ★690 | sql/nosql | entity generator, built on Knex similar to activerecord |

## Reverse Proxy
## Authentication
[Open Id Connect (OIDC)](https://auth0.com/docs/protocols/oidc) protocol. Lets users connect using external service (e.g. Facebook, Google) or local account. Makes use of Javascript Web Tokens (JWT). These are already contained in many of the starter applications, but listed here for completeness.

| Package | Stars | Description |
| ------- | -----:| ----------- |
| [Passport](http://www.passportjs.org/)💗 | ★17.2k | authentication middleware for Node.js |
| [Everyauth](https://github.com/bnoguchi/everyauth) | ★3.5k | Allows authorization using facebook, google, etc. Cool but old and passport does all of this |


## External Login
## Authorization
## Secure Socket
Node `npm add https` handles this but needs a certificate.

| Package | Stars | Description |
| ------- | -----:| ----------- |
| [Lets Encrypt](https://letsencrypt.org/) | | A free certificate authority for deploying `HTTPS`. An article on how to use it is [here](https://dev.to/omergulen/step-by-step-node-express-ssl-certificate-run-https-server-from-scratch-in-5-steps-5b87) |
| [Self Signed Certificate](https://timonweb.com/posts/running-expressjs-server-over-https/) | | You can also create a self signed certificate using `openssl` which appears to standard in my linux system |

## CORS Support
## Logging
## Load Balancer
## Rate Limiting
To protect from overloading, rate limiting is needed. [This Article](https://blog.logrocket.com/rate-limiting-node-js/) explains it nicely. The packages below look similar in their capabilities and approach. 

| Product | Stars | Description |
| ------- | -----:| ----------- |
| [express-rate-limit](https://github.com/nfriedly/express-rate-limit) | ★1.3k | Basic rate-limiting middleware for Express. Use to limit repeated requests to public APIs and/or endpoints such as password reset. Needs external data store for robustness. |
| [bottleneck](https://github.com/SGrondin/bottleneck) | ★892 | Bottleneck is a lightweight and zero-dependency Task Scheduler and Rate Limiter for Node.js and the browser. |
| [node-rate-limiter-flexible](https://github.com/animir/node-rate-limiter-flexible)💗 | ★838 | rate-limiter-flexible counts and limits number of actions by key and protects from DDoS and brute force attacks at any scale. |
| [express-brute](https://github.com/AdamPflug/express-brute) | ★484 | A brute-force protection middleware for express routes that rate-limits incoming requests, increasing the delay with each request in a fibonacci-like sequence. |
| [express-limiter](https://github.com/ded/express-limiter) | ★400 | OLD Rate limiting middleware for Express applications built on redis |

## Analytics
There are many, and often provided by web hosting company. The more popular ones are Google and Yahoo which are free. Paid solutions exist. Do a search for more information.

| Package | Stars | Description |
| ------- | ----- | ----------- |
| [Google](http://google.com/analytics) | Free | |
| [Yahoo](http://web.analytics.yahoo.com/) | Free | |

## SEO

# Prebuilt Servers

1. [Node](Node.md)
2. [API Gateways](Gateway.md)
3. [Docker](Docker.md)
4. [Go](AwesomeGo.md)


[Next> Deployment](../Deployment/Deployment.md)