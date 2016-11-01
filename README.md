# Swarm-Cluster
Virtual box + Vagrant + Ansible to setup a base swarm cluster (docker 1.12+)

## Prerequisites
**Virtual Box 5.1.8 r111374 (Qt5.6.1)**

[Virtualbox](https://www.virtualbox.org/wiki/Linux_Downloads)

**Vagrant 1.8.6**

[Vagrant](https://www.vagrantup.com/downloads.html)


**Ansible 2.1.2.0**

	$ sudo apt-get update
	$ sudo apt-get install software-properties-common
Once the package is installed, we can add the Ansible PPA by typing the following command:

	$ sudo apt-add-repository ppa:ansible/ansible (Press ENTER to accept the PPA addition.)
Next, we need to refresh our system's package index so that it is aware of the packages available in the PPA. Afterwards, we can install the software:

	$ sudo apt-get update
	$ sudo apt-get install ansible

##Usage
Create Cluster's Machines with **Virtualbox** and provision with **Ansible**

	$ Vagrant up [wait util cluster is built]


##Command
Show Cluster’s nodes

	$ docker node ls


Create a Service named **whoami**

	$ docker network create --driver overlay go-demo

	$ docker service create --network go-demo -p 8000:8000 --name whoami  jwilder/whoami 

	$ docker service ls

	$ docker service ps whoami


	$ docker inspect <container-id>

	$ docker network ls

	$ docker service ps whoami


# Scale Service
	$ docker service update --replicas 5 whoami

##Credits
[Github-Uncharted89](https://github.com/Uncharted89/swarm-base-ansible)

[Docker Swarm Introduction](https://technologyconversations.com/2016/07/29/docker-swarm-introduction-tour-around-docker-1-12-series/)

[microservice](http://blog.alexellis.io/microservice-swarm-mode/)

[whoami](https://hub.docker.com/r/jwilder/whoami/)
##Licence


Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License.

You may obtain a copy of the License at [Apache License](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
