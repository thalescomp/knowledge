# General Concepts

## NGINX

HTTP/web server and reverse proxy

## `ps` command

Used to provide information about the currently running processes, including their process identification numbers` (PIDs).

## DPKG

The software at the base of the package management system in the free operating system Debian and its numerous derivatives. `dpkg` is used to install, remove, and provide information about .deb packages.


# Docker

Docker is an open platform for developing, shipping, and running applications. Docker enables you to separate your applications from your infrastructure so you can deliver software quickly. With Docker, you can manage your infrastructure in the same ways you manage your applications. By taking advantage of Docker’s methodologies for shipping, testing, and deploying code quickly, you can significantly reduce the delay between writing code and running it in production.

## Container

A container is a standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably from one computing environment to another. It's an abstraction at the app layer that packages code and dependencies together. Multiple containers can run on the same machine and share the OS kernel with other containers, each running as isolated processes in user space. Containers take up less space than VMs (container images are typically tens of MBs in size), can handle more applications and require fewer VMs and Operating systems.

## Container Image

A Docker container image is a lightweight, standalone, executable package of software that includes everything needed to run an application: code, runtime, system tools, system libraries and settings.

Container images become containers at runtime and in the case of Docker containers - images become containers when they run on Docker Engine. Available for both Linux and Windows-based applications, containerized software will always run the same, regardless of the infrastructure. Containers isolate software from its environment and ensure that it works uniformly despite differences for instance between development and staging.

## Commands

1. `docker pull <image>`. Install container image from Docker Hub.
1. `docker images`. Show current container images.
1. `docker run -d <image>`. Run a container image if it doesn't exist, it is installed. When an container image is running, it's a container itself in memory` (`-d`: run container in background and print container ID).
1. `docker ps`. Show running containers.
1. `docker ps -a` or `docker ps --filter "status=exited"`. First: show both stopped and running containers. Second: show just stopped containers.
1. `docker inspect <container:id>`. Find more info about a specific container` (Ex: IPAddress, so on).


# Kubernetes

Portable, extensible, open-source platform for managing containerized workloads and services, that facilitates both declarative configuration and automation. It has a large, rapidly growing ecosystem. Kubernetes services, support, and tools are widely available.

## Pods

A Pod is the basic execution unit of a Kubernetes application–the smallest and simplest unit in the Kubernetes object model that you create or deploy. A Pod represents processes running on your Cluster .

A Pod encapsulates an application’s container (or, in some cases, multiple containers), storage resources, a unique network IP, and options that govern how the container(s) should run. A Pod represents a unit of deployment: a single instance of an application in Kubernetes, which might consist of either a single container or a small number of containers that are tightly coupled and that share resources.

## Node

A node is a worker machine in Kubernetes, previously known as a minion. A node may be a VM or physical machine, depending on the cluster. Each node contains the services necessary to run pods and is managed by the master components. The services on a node include the container runtime, kubelet and kube-proxy. See The Kubernetes Node section in the architecture design doc for more details.

## Service

An abstract way to expose an application running on a set of Pods as a network service.

With Kubernetes you don’t need to modify your application to use an unfamiliar service discovery mechanism. Kubernetes gives Pods their own IP addresses and a single DNS name for a set of Pods, and can load-balance across them.

## Commands

1. `kubectl run <podname> --image=<container image name:version>`. Launch a single instance.
1. `kubectl get pods`. Examine pods.
1. `kubectl expose deployment <instance name> --port 80 --type LoadBalancer`. Expose instance.
1. `kubectl get services`. List services.
1. `cat pods/monolith.yaml`. Explore config file.
1. `kubectl create -f pods/monolith.yaml`. Create the monolith pod.
1. `kubectl describe pods monolith`. +Info about a pod.
1. `kubectl describe services monolith | grep Endpoints`. +Info about a service.
1. `kubectl port-forward monolith 10080:80`. Set pod to a local IP Address.
1. `kubectl logs monolith`. View logs of a pod.
1. `kubectl exec monolith --stdin --tty -c monolith /bin/sh`. Run an interactive shell inside the monolith Pod.
1. `kubectl create secret generic tls-certs --from-file=tls/`. Create the tls-certs secret from the TLS certificates stored under the tls directory. Kubectl will create a key for each file in the tls directory under the tls-certs secret bucket.
1. `kubectl create configmap nginx-proxy-conf --from-file=nginx/proxy.conf`. Create configmap.
1. `kubectl create -f services/monolith.yaml`. Create a service.
1. `kubectl get pods -l "app=monolith"`. Get pods based on labels.
1. `kubectl label pods secure-monolith "secure=enabled"`. Label a pod.
1. `kubectl create -f deployments/auth.yaml`. Create the auth deployment.