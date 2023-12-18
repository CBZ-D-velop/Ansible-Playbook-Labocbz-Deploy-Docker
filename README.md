# Ansible playbook: labocbz.deploy_docker

![Licence Status](https://img.shields.io/badge/licence-MIT-brightgreen)
![CI Status](https://img.shields.io/badge/CI-success-brightgreen)
![Testing Method](https://img.shields.io/badge/Testing%20Method-Ansible%20Molecule-blueviolet)
![Testing Driver](https://img.shields.io/badge/Testing%20Driver-docker-blueviolet)
![Language Status](https://img.shields.io/badge/language-Ansible-red)
![Compagny](https://img.shields.io/badge/Compagny-Labo--CBZ-blue)
![Author](https://img.shields.io/badge/Author-Lord%20Robin%20Crombez-blue)

## Description

![Tag: UNIX](https://img.shields.io/badge/Tech-UNIX-orange)
![Tag: Ansible](https://img.shields.io/badge/Tech-Ansible-orange)
![Tag: Debian](https://img.shields.io/badge/Tech-Debian-orange)
![Tag: Docker](https://img.shields.io/badge/Tech-Docker-orange)
![Tag: docker-compose](https://img.shields.io/badge/Tech-docker--compose-orange)
![Tag: portainer](https://img.shields.io/badge/Tech-portainer-orange)
![Tag: watchtower](https://img.shields.io/badge/Tech-watchtower-orange)

An Ansible playbook to install and configure Docker, docker-compose and other tools on a server based on Debian/Ubuntu.

This Ansible playbook streamlines the deployment of essential containerization tools: Docker, Docker Compose, Portainer, and Watchtower. Containerization has become a fundamental technology in modern IT environments, enabling efficient software deployment, scaling, and management.

The playbook leverages predefined roles to simplify the installation and configuration of these tools. Here's what each tool brings to the table:

1. **Docker:** Docker is a leading containerization platform that allows you to package and distribute applications as containers. It provides a consistent environment for applications, making it easier to manage dependencies and isolate processes.
2. **Docker Compose:** Docker Compose simplifies multi-container application orchestration. You can define complex application stacks in a single YAML file, making it easier to manage and scale multi-container applications.
3. **Portainer:** Portainer is a user-friendly Docker management interface that simplifies container management tasks. It offers a web-based dashboard, making it easier to visualize and manage containers, networks, and volumes.
4. **Watchtower:** Watchtower is an automated update tool for Docker containers. It continuously monitors your Docker containers and updates them with the latest versions when they become available, helping you maintain the security and stability of your containerized applications.

This playbook allows you to customize the deployment of these tools according to your specific requirements. Whether you're building a microservices architecture, managing a containerized application stack, or simply looking for efficient ways to work with containers, this playbook streamlines the process.

By using Ansible with this playbook, you ensure consistent and efficient deployment of Docker, Docker Compose, Portainer, and Watchtower across your infrastructure. It simplifies the setup and maintenance of containerized applications, promoting better scalability, security, and management.

## Deployment diagramm

## Tests and simulations

### Basics

You have to run multiples tests. *tests with an # are mandatory*

```MARKDOWN
# lint
# syntax
# converge
# idempotence
# verify
side_effect
```

Executing theses test in this order is called a "scenario" and Molecule can handle them.

Molecule use Ansible and pre configured playbook to create containers, prepare them, converge (run the playbook) and verify its execution.
You can manage multiples scenario with multiples tests in order to get a 100% code coverage.

This playbook contains a ./tests folder. In this folder you can use the inventory or the tower folder to create a simualtion of a real inventory and a real AWX / Tower job execution.

### Command reminder

```SHELL
# Check your YAML syntax
yamllint -c ./.yamllint .

# Check your Ansible syntax and code security
ansible-lint --config=./.ansible-lint .

# Execute and test your playbook
molecule lint
molecule create
molecule list
molecule converge
molecule verify
molecule destroy

# Execute all previous task in one single command
molecule test
```

## Installation

To install this playbook, just copy/import this playbook or raw file into your fresh playbook repository or call it with the "include_playbook/import_playbook" module.

## Usage

### Vars

```YAML
# From inventory
---
# all vars from to put/from your inventory
# see tests/inventory/group_var for all groups and vars.
```

```YAML
# From AWX / Tower
---
tower_env: "local"
```

## Architectural Decisions Records

Here you can put your change to keep a trace of your work and decisions.

### 2023-09-23: First Init

* First init of this playbook with the bootstrap_playbook playbook by Lord Robin Crombez
* Playbook install Docker, docker-compose
* Portainer and Watchtower can be installed, or not

### 2023-10-06: New CICD, new Images

* New CI/CD scenario name
* Molecule now use remote Docker image by Lord Robin Crombez
* Molecule now use custom Docker image in CI/CD by env vars
* New CICD with needs and optimization

### 2023-11-11: Prepare Host and Boolean

* Prepare host is now called
* You can install or not with a boolean value

### 2023-12-18: Prepare Host and Boolean 2

* Prepare host is now called
* You can install or not with a boolean value

## Authors

* Lord Robin Crombez

## Sources

* [Ansible playbook documentation](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_reuse_playbooks.html)
* [Ansible Molecule documentation](https://molecule.readthedocs.io/)
* [labocbz.install_docker](https://github.com/CBZ-D-velop/Ansible-Role-Labocbz-Install-Docker.git)
