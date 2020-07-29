# Prebuilt API Gateways
An API Gateway sits in front of your application(s) and manages the heavy lifting of authorisation, access control and throughput limiting to your services. Ideally, it should mean that you can focus on creating services instead of implementing management infrastructure.

**TLDR;**
- API Gateways are big, expensive heavy things that make sense if you need them.
- Caddy appears to handle most of the heavy lifting
- Consult the others as necessary
- Some of these are big and expensive!

| Product | Stars | Description |
| ------- | -----:| ----------- |
| [Traefik](https://github.com/containous/traefik/) | ★29.0k | Traefik is an open-source **Edge Router** that receives requests on behalf of your system and finds out which components are responsible for handling them. What sets Traefik apart, besides its many features, is that it automatically discovers the right configuration for your services. The magic happens when Traefik inspects your infrastructure, where it finds relevant information and discovers which service serves which request. NOTE: Useful if you have a complex network with a lot of services. It is a bit too heavy for what I need at this time. |
| [Caddy](https://caddyserver.com/)💗 | ★27.4k | It takes care of TLS certificate renewals, OCSP stapling, static file serving, reverse proxying, **Kubernetes ingress**, and more. This appears to be a web server with all the bits, ready to go, out of the box. It is not strictily an API gateway, but it reports to have one. Unfortunately, it is in the process of switching over from v1 to v2 2020.05.01 and it needs time to stabilize. They changed the way their modules work, so v2 does not have as good support as v1. |
| [Kong](https://github.com/Kong) | ★25.1k | A full meal deal web site server uses openresty |
| [k3s](https://k3s.io/) | ★12.6k | A simplified / lightweight kubernetics k8s with all the bells and whistles. Image is <100M and it can be deployed everywhere from IoT to large edge devices. |
| [Tyk](https://github.com/TykTechnologies/tyk) | ★5.3k | Newer than kong and written in GO |
| [KrakenD](https://github.com/devopsfaith/krakend) | ★2.7k | caddy alternative. It is an API Gateway that offers: Monitoring(logging,stats); Security (SSL,policies); Proxy(OAuth,protocol translation,load balancing); QoS(concurrent calls,circuit breaker,grained timeout); Cache; Aggregation(from multiple sources); Manipulation; Filtering(whilelist,blacklist);Decoding. It rates 18k responses per second on a laptop, and around 3k-10k/s on an amazon server. It is 2x faster than Kong and 10x faster than Tyk. It is easy to set up and has a visual API designer. |
| [express gateway](https://www.express-gateway.io/) | ★2.0k | A microservices API Gateway built on top of Express.js |
| [openresty](https://openresty.org/en/) | ★1.1k | dynamic web platform based on NGINX. Tons of plugins and look complicated. Written in Lua |
| [Swarmlet](https://swarmlet.dev/) | ★138 | BETA: Incorporates a set of other projects into docker-composed containers to result in a complete web server that handles all the bits - along with monitoring. It simply automates what a lot of devOps are doing manually. Work in progress and only released around 2020.05.01 **VERDICT** this will work well with my planned custom docker to add extra features that are missing. |
