# GNS3-testing
The purpose of this is automating the deployment of development GNS3 versions so testers can launch a new environment quickly. It uses Vagrant to set up a remote GNS3 server and a client VM (GUI) pair.

## Usage
The VMs have a private network that they use to communicate with each other. IP addresses:
* Server: 172.19.139.10
* Client: 172.19.139.11

Credentials: vagrant / vagrant

The GNS3 GUI on the client is preconfigured, all you need to do is import the appliances and create a project.

## Limitations
Vagrant uses VirtualBox as provider because that's free and commonly used. However nested virtualization support is limited; hence you should avoid running CPU intensive QEMU VMs. You can still use the following:
* Docker containers
* Dynamips routers
* IOU devices
* Lightweight QEMU VMs
