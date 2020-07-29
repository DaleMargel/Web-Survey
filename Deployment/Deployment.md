# Deployment

## Containers
Docker seems to be the way to go for containers. Also check out [DockerHub](https://hub.docker.com/). Kubernetics makes more sense when you have a million users and need high-quality container capabilities. For now, we will start with **docker-compose** which can be used by kubernetcs when we get those million users...

| Package | Stars | Description |
| ------- | -----:| ----------- |
| [kubernetics](https://github.com/kubernetes/kubernetes) | ★65.7k | Very high end container orchestration with a more complex API. More popular and more widely supported than Docker Swarm |
| [Docker Compose](https://github.com/docker/compose)💗 | ★19.2k | Define and run multi-container applications on a single machine. The docker-compose.yaml file can easily be translated to kubernetics of needed as a good starting point. DC can be deployed on:  |
| [Docker Swarm](https://github.com/docker/swarmkit) | ★2.4k | Define and run multi-container applications distributed over multiple machines |

Aside: [Alpine](https://github.com/gliderlabs/docker-alpine) (★5.3k) is the most popular docker image - 5Mb. This makes containers relatively small and fast.

## Host Server

| Name | Deployment |
| ---- | ---------- |
| Heroku | The Heroku platform uses Git as the primary means for deploying applications. [Good writeup here](https://blog.heroku.com/six-strategies-deploy-to-heroku), accepts Docker containers. Heroku uses (sits on top of) AWS and is more expensive. |
| DigitalOcean | | 
| Amazon ECS | |
| Amazon EKS | AWS managed Kubernetes cluster of master servers |
| Google Cloud (GCP) | |
| Microsoft Azure | |
| Linux Server | |