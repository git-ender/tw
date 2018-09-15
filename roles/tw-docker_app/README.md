# tw-docker_app

This role is just and exercise. It builds a docker image from a dockefile on remote hosts and start a container from it.


# Requirements

* Ansible >= 2.1
* Python >= 2.6
* Docker-py >= 1.7.0
* Docker API >= 1.20

# Role Variables

See default/main.yml for example

container: "container to be started"
image: "use clojure for building"
tag: "latest"
#exposed_ports: 
published_ports: "mapped ports on container and hosts"
ipv4: "an ip for container, useful for future improvement"

# Network section
network_name: "MyNet"
subnet_class: "subnet, useful for future improvemen"

# general vars
dockerfile_path: "local path for docker file"
remote_dockerfile_path: "remote path for docker file"


# Known issues
There is some issues with Ansible 2.6.x. See https://github.com/ansible/ansible/issues/42162
