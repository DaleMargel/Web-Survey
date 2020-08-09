# Prebuilt Node Servers
These are some express-based starter kits, kindly provided by a [medium article](https://medium.com/better-programming/best-node-js-boilerplate-to-speed-up-your-project-development-a9eca7b07f90). Also list at https://github.com/topics/express-boilerplate and https://dev.to/sm0ke/nodejs-starter-javascript-boilerplates-to-start-fast-1024. These are sorted by star order. Some have been removed.

The features to look for:
- Overall { simplicity, easy to understand, layout, design, docs, wow-factor }
- Login { login, signup, external, forgot, mail }
- Rest or Graphql { clean interface or automatically generated }
- Database { SQL or NoSQL }
- Frontend { React or Preact with style }
- Testing { Unit, API, E2E testing }
- Hosting { Docker or other container }

While these are written to be front-end servers, we may choose to employ one or more of these as a service. The code here should be reviewed more closely when I have a better idea of how I wish to structure the application.

The prize seems to be a toss between [diegohaz/ rest](https://github.com/diegohaz/rest) and [FredericHeem/ starhackit](https://github.com/FredericHeem/starhackit). Both of these have great features that the other misses. It would be ideal to combine them both. Probably start with Diegohaz and mix in the goodness from FredericHeem.

Note: Diegohaz looks like it uses Flux. If so, all the better.

| Product | Stars | Description |
| ------- | -----:| ----------- |
| [sahat/ hackathon](https://github.com/sahat/hackathon-starter)💗 | ★29.8k | A boilerplate for building Node.js web applications at hackathons. Contains OICD logins for {google, facebook, twitter, github, linkedin and instagram}, back end mongo, contact form, forgot password handling and a bunch of other goodies that are commonly needed on commercial grade sites. Great reference information! <br>**VERDICT** handles user account management with rest. Very good starting point for app that requires elaborate login handling.<br><br>  |
| [kriasoft/ react](https://github.com/kriasoft/react-starter-kit) | ★20.0k | Related to [kriasoft/ nodejs](https://github.com/kriasoft/nodejs-api-starter); an opinionated boilerplate for web development built on top of Node.js, Express, GraphQL and React |
| [Flux](https://github.com/facebook/flux) ▶ | ★16.7k | [Main Page](http://facebook.github.io/flux/) More of a pattern than a framework. This is the way that Facebook builds apps. It looks a bit formalized, but perhaps is the way to go. |
| [kriasoft/ nodejs](https://github.com/kriasoft/nodejs-api-starter) | ★2.8k | Boilerplate and tooling for authoring (serverless) data API back ends with Node.js and GraphQL. It is best suited for developing a GraphQL API endpoint as a standalone (micro)service, backing up web front-ends and/or mobile applications. <br>**USEFUL** This makes use of [membership db](https://github.com/membership/membership.db) which contains standard boiler plate for user accounts. |
| [developit/ express es6 rest](https://github.com/developit/express-es6-rest-api) | ★2.3k | This is a straightforward boilerplate for building REST APIs with ES6 and Express. |
| [talyssonoc/ node api](https://github.com/talyssonoc/node-api-boilerplate)💗 | ★2.2k | DDD/Clean Architecture inspired boilerplate for Node web APIs. <br>**VERDICT:** This one has the best vision. It makes use of DI, GraphQL, nicely set up express, squelize orm (Postgres, but can use any SQL ), logging, testing, linting. Basically all the bells and whistles without too much complexity. It is mostly from 2018, but is reasonably universal in the way it works. |
| [expressjs/ express generator](https://github.com/expressjs/generator) | ★1.4k | The standard generator, not great but not bad either. Uses pug... |
| [diegohaz/ rest](https://github.com/diegohaz/rest)💗 | ★1.3k | REST API generator with Node.js, Express and Mongoose. <br>**VERDICT:** Definitely, it is a builder that generates a reasonably compact rest server. You add routes via commandline. If you need a rest server with mongo, this is what you want to use. |
| [madhums/ node express mongo](https://github.com/madhums/node-express-mongoose) | ★1.2k | A boilerplate application for building web apps using node and mongodb |
| [FredericHeem/ starhackit](https://github.com/FredericHeem/starhackit)💗 | ★1.2k |  StarHackIt: React/Native/Node fullstack starter kit with authentication and authorization, data backed by SQL. <br>**VERDICT** WOW! Big, but extremely complete including E2E and REST generation! I am drooling over it. |
| [danielfsousa/ express rest es2017](https://github.com/danielfsousa/express-rest-es2017-boilerplate)| ★1.2k | Boilerplate/Generator/Starter Project for building RESTful APIs and microservices using Node.js, Express and MongoDB (with no transpilers!!) <br>**VERDICT:** NO TRANSPILERS!! Simple, but seems to have all of the main features I am looking for. |
| [inadarei/ node bootstrap](https://github.com/inadarei/nodebootstrap/) | ★701 | generates skeleton project for Node/Express.js with pre-configured best-practices. The github contains just a javascript file that generates your workspace.  |
| [maitraysuthar/ rest api nodejs mongodb](https://github.com/maitraysuthar/rest-api-nodejs-mongodb) | ★404 | ES2015, MVC-centric, pass... |
| [cosmicjs/ nodejs website](https://github.com/cosmicjs/nodejs-website-boilerplate) | ★149 | Polished, but basic html only |
| [ngduc/ node rem](https://github.com/ngduc/node-rem) | ★145 | NodeJS Rest Express MongoDB and more: typescript, passport, JWT, socket io, HTTPS, HTTP2, async/await, nodemailer, templates, pagination, docker, etc. <br>**VERDICT:** Server only, but it has all the bits without too many files, good handling or REST routing. |
| [ridhamtarpara/ express es8 rest](https://github.com/ridhamtarpara/express-es8-rest-boilerplate) | ★73 | Node.js boilerplate for building RESTful APIs using Express, MongoDB, Passport, Mocha using ES2017(ES8) syntax. <br>**VERDICT:** a lot of features, but few files... |
| [hagopj13/ node express mongoose ](https://github.com/hagopj13/node-express-mongoose-boilerplate) | ★56 | Very similar to [imbudhiraja/ express](https://github.com/imbudhiraja/express-boilerplate). which I like. <br>**VERDICT:** simple and pragmatic, but covers all that is needed. | 
| [eldimious/ nodejs](https://github.com/eldimious/nodejs-api-showcase) | ★38 |  Node.js App Architecture showcase heavily influenced by the Clean Architecture and Hexagonal Architecture, using MongoDB. <br>**VERDICT:** good clean architure model, but seems to need a lot of files too. |
| [imbudhiraja/ express](https://github.com/imbudhiraja/express-boilerplate) | ★25 | ExpressJS boilerplate with Socket IO, Mongoose for scalable projects. <br>**VERDICT:** Similar to [hagopj13/ node express mongoose ](https://github.com/hagopj13/node-express-mongoose-boilerplate), I like this one. It is simple and pragmatic, but covers most areas that are needed. |
| [adamkarb/ xpb](https://github.com/adamkarb/xbp) | ★3 | Basic starter for express + mongo. <br>**VERDICT:** Better than the stars would have you believe, but too basic for what I need. |
| [fedoryakubovich/ express mongodb](https://github.com/fedoryakubovich/express-mongodb-boilerplate) | ★2 | Pragmatic features and layout. <br>**VERDICT** Deserves more stars, but is basic mongo, rest, and login. Too basic really...  |
| [pjt3591oo/ react express](https://github.com/pjt3591oo/react-express-boilerplate) | ★1 | react - express 조합 boilerplate <br>**VERDICT** seems to have many of the parts, simple, not bad at all! |
| [omidnavy/ child process express](https://github.com/omidnavy/nodejs-child-process-express-boilerplate) | ★0 | Just an example: Using express as a child process in a Node.js app, where the child has n

# Deno
[Deno](https://deno.land) is a modern replacement for Node.js, written by the same author.

| Product | Stars | Description |
| ------- | -----:| ----------- |
| [Server](https://deno.land/std@0.63.0/http/server.ts) | | This is the standard deno server. It is about the same speed as Node, and it supports HTTPS directly (with some setup) |
| [Oak](https://deno.land/x/oak@v6.0.1) | ★2.3k | A popular Deno web server. It extends Server and takes inspiration from Koa |
| [Nexo](https://deno.land/x/nexo@v0.1.1)⚑ | ★1 | This one deserves special mention. It reports to render static fragments on the server and dynamic fragments on the client. It uses Preact (which I like) and [Otion](https://github.com/kripod/otion), a "atomic css-in-js" styling library. **NOTE**: I was unable to get this working out of the box. It seems to depend on a library in Deno which is no longer there.  |