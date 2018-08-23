# from-docker-to-kubernetes

Simple guide to get started in kubernetes using minikube


## Dockerfile

### Build and run flask 

$ cd docker

$ docker build . -t 'flask'

$ docker run -d flask


Check running docker


$ docker ps


## Docker-compose

[Docker-compose](https://docs.docker.com/compose/) It's a tool for definning and running multi-container docker applications

Starts the services:

$ docker-compose up

Shutdowns services

### Scaling up

With this command we scale up to have 5 flask web servers and one caddyfile proxy to send them traffic and auto-balance between them

  $ docker-compose scale web=5 server=1


## Kubernetes

Let's start kubernetes with minikube

[Minikube](https://kubernetes.io/docs/setup/minikube/) it's a tool to run locally kubernetes 


Here we start the minikube local cluster

$ minikube start


For checking the kubernetes dashboard

$ minikube dashboard


### Deploying docker-compose to kubernetes


Inside docker with our docker-compose.yml file we will use [kompose](http://kompose.io/) to deploy the containers:

$ kompose up


This pushes the images and deploy then in the kubernetes cluster

$ kompose convert 


Convert files to kubernetes files
