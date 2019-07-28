DOCKER - Open source tool that makes easy to create, distribute and run applications. It does it by packaging applications in a set of container images.
# Commands
> docker pull <image> (install container image from Docker Hub)
> docker images (show current container images)
> docker run -d <image> (run container image if it doesn't exist, it is installed. When an container image is running, it's a container itself) [-d Run container in background and print container ID]
> docker ps (show running containers)
> docker ps --filter "status=exited" (show stopped containers) OR docker ps -a (show both stopped and running)
> docker inspect <container:id> (find more info about a specific container. Ex: IPAddress)


NGINX - HTTP/web server and reverse proxy

PS COMMAND - used to provide information about the currently running processes, including their process identification numbers (PIDs).

DPKG - the software at the base of the package management system in the free operating system Debian and its numerous derivatives. dpkg is used to install, remove, and provide information about .deb packages.

Containers - Technology that makes it easy to run and distribute applications across different operating environments


KUBERNETES - ?
# Commands
> kubectl run <podname> --image=<container image name:version> (Launch a single instance)
> kubectl get pods (Examine pods)
> kubectl expose deployment <instance name> --port 80 --type LoadBalancer (Expose instance)
> kubectl get services (list services)
> cat pods/monolith.yaml (Explore config file)
> kubectl create -f pods/monolith.yaml (Create the monolith pod)
> kubectl describe pods monolith (+Info about a pod)
> kubectl port-forward monolith 10080:80 (Set pod to a local IP Address)
> kubectl logs monolith (View logs of a pod)
> kubectl exec monolith --stdin --tty -c monolith /bin/sh (Run an interactive shell inside the monolith Pod)
> kubectl create secret generic tls-certs --from-file=tls/ (Create the tls-certs secret from the TLS certificates stored under the tls directory. Kubectl will create a key for each file in the tls directory under the tls-certs secret bucket.)
> kubectl create configmap nginx-proxy-conf --from-file=nginx/proxy.conf (Create configmap)
> kubectl create -f services/monolith.yaml (Create a service)
> kubectl get pods -l "app=monolith" (Get pods based on labels)
> kubectl label pods secure-monolith "secure=enabled" (Label a pod)
> kubectl describe services monolith | grep Endpoints (+Info about a service)
> kubectl create -f deployments/auth.yaml (Create the auth deployment)

PODS - It has an IP Address by default