# Install Docker On Debian Servers
## Intro
Those playbooks aim to install a Docker on multiple debian servers and setup a Docker Swarm on those servers. Optionally, the last file will install a Portainer stack on the cluster. 

## How to

### Install of Docker

First of all, you need to CD inside the playbooks folder, and edit the hosts file to make it match with your servers IP configurations. Then you have to run the first playbook called *1Docker-Dependances.yml* to install the dependencies required by Docker. Them you have to run *2Docker-Install.yml*. This playbook will add the PGP of the Docker official repositeries, next it will add the repo address to the *source.list* file of your Debian servers and finally, it will install 
* docker-ce
* docker-ce-cli
* containerd.io

### Creation of the swarm

The third playbook *3swarm_init.yml*, once exectuted on the server you have decided to promote as a manager, will initialize the Swarm and display the command you'll have to add in the file *4swarm_join.yml* after the last comment. Once the *yml* filed edited, run the playbook. Wait until the end of the script. 

### Enjoy 😁

## Optional step

### Portainer Stack
Portainer is a lightweight management UI which allows you to easily manage your Docker host or Swarm cluster. Portainer is meant to be as simple to deploy as it is to use. It consists of a single container that can run on any Docker engine (Docker for Linux and Docker for Windows are supported).
The last playbook *5portainer_stack.yml* will create and launch a Portainer container on your freshelly created swarm. Just run it and enjoy.

# Have fun
The BAEthernet Team.
