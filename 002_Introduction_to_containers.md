# Virtual Machine Vs Container

#### 1. What is Virtual Mechaine

* Virtual machines (VMs) are an abstraction of physical hardware turning one server into many servers. The hypervisor allows multiple VMs to run on a single machine. Each VM includes a full copy of an operating system, one or more apps, necessary binaries and libraries - taking up tens of GBs. VMs can also be slow to boot.


#### 2. What is Container

* Containers are an abstraction at the app layer that packages code and dependencies together. Multiple containers can run on the same machine and share the OS kernel with other containers, each running as isolated processes in user space. Containers take up less space than VMs (container images are typically tens of MBs in size), and start almost instantly.

#### Note:
##### Containers On cloud providers are still bit different than just running a container on the host operating system, Beacause cloud proviers still use hypervisor to isolate the customers from each other, But you will still get the all the benifits of containerazation, The following figure show the structure of a containers on cloud

![Virtual Machine Vs Container](https://i.imgur.com/vV2H20Z.png)

### Virtual Machine Versus Container:

![Virtual Machine Vs Container](http://cdn.ttgtmedia.com/rms/onlineImages/windows_server-virtual_machines_vs_containers.png)

### Docker:

+ Docker is the most popular container software, An alternative to Docker is rkt - which also works with Kubernetes

### Docker Engine:

+ Docker consists of Docker Engine, It's Docke runtime.
+ Docker Engine is a software to make run the Docker images
+ Using Docker Engine we can also build Docker images to then run on Kubernetes cluster.

### Docker Hub:

+ Docker Hub is a online service to store and fetch Docker images
+ Docker Hub has both public and private repositories for storing Docker Images
+ Docker Hub also allows us to build the images online so that we no need to build them on PC.
+ The cloud providers themselvs also have alternative to Docker Hub Ex: AWS has it's own repositories where we can see Docker images.
+ You can also run your own Docker Hub, You can run your own repositories, If you would like to.

### Docker Benifits:

+ Isolation: you ship a binary with all dependencies 
                - no more it works on my machine, but not in production
+ Docker Development teams able to ship faster ( Can create and distribute images quickly )
+ You can run the same Docker image, unchanged, on laptops, data centre VMs, and Cloud providers 
+ Docker uses Linux Containers ( a kernel feature) for operating system-level isolation
+ It's a ship with containers on it. So, basically with containerization builds your container, in that exact same state, so you can run it wherever you want. The container contains all of dependencies, so it should execute exactly the same ( When you run it locally or cloud on Kubernetes or anywhere you want to run it.



