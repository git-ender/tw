# tw-docker_app
This role is just and exercise. It builds a docker image from a dockefile on remote hosts and start some containers from it, acconding to config files.

# Requirements

* Ansible >= 2.1
* Python >= 2.6
* Docker-py >= 1.7.0
* Docker API >= 1.20

# Role Variables

See default/main.yml for example. Ansible use a dict file for providing variables for all the containters. Ansible will fail if "*_ports" variables are empty so leave them commented if you do not want to use it (see tasks for details).

    containers:
      "tw_docker_container_1":
        image: "clojure"
        tag: "latest"
        working_dir: "{{ common_path }}/my_app_path"
        env_file_name: "env_file_1"
        exposed_ports: ""
        published_ports: ""
        command: "java -jar my_app_1"
        ipv4: "x.x.x.x"

    # Network section
    network_name: "TW-Net"
    subnet_class: "x.x.x.x/xx"

    # General vars
    image: "clojure"
    tag: "latest"

    git_repo: "repo_url_for_retrieving_config_files"
    config_file_path: "path_to_docker_and_env_files"
    temp_repo_path: "path_to_store_repe"
    common_path: "my_general_path"

# Known issues
There is some issues with Ansible 2.6.x. See https://github.com/ansible/ansible/issues/42162
