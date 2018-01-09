# Virtual Machine Vs Container

#### 1. What is Virtual Mechaine

* Virtual machines (VMs) are an abstraction of physical hardware turning one server into many servers. The hypervisor allows multiple VMs to run on a single machine. Each VM includes a full copy of an operating system, one or more apps, necessary binaries and libraries - taking up tens of GBs. VMs can also be slow to boot.


#### 2. What is Container

* Containers are an abstraction at the app layer that packages code and dependencies together. Multiple containers can run on the same machine and share the OS kernel with other containers, each running as isolated processes in user space. Containers take up less space than VMs (container images are typically tens of MBs in size), and start almost instantly.

#### Note: Containers On cloud providers are still bit different than just running a container on the host operating system, Beacause cloud proviers still use hypervisor to isolate the customers from each other, The following figure show the structure of a containers on cloud

![Virtual Machine Vs Container](https://i.imgur.com/vV2H20Z.png)

![Virtual Machine Vs Container](http://cdn.ttgtmedia.com/rms/onlineImages/windows_server-virtual_machines_vs_containers.png)



