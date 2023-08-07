# Docker Compose Setup for Connect Ubuntu Container Via SSH

This Repository Contains a Docker Compose Setup that creates multiple instance ready to use with unique Name, And Auto-Incremented ports numbers.

## Overview

The purpose of this project is to simulate a multi-node server environment for testing software that manages and configures remote servers. This setup is particularly useful for developers and testers who need to validate software behavior in a distributed system.

## Getting Started

Follow these steps to set up and use the multi-node server testing environment:

## Prerequisites

- Docker
  - sudo apt install apt-transport-https ca-certificates curl software-properties-common
  - curl -fsSL <https://download.docker.com/linux/ubuntu/gpg> | sudo apt-key add -
  - sudo add-apt-repository "deb [arch=amd64] <https://download.docker.com/linux/ubuntu> focal stable"
  - sudo apt update && sudo apt install docker-ce
  - sudo usermod -aG docker ${USER} && su - ${USER}
  - sudo service docker start
  - docker ps
- Docker Compose
  - sudo curl -L "<https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname> -s)-$(uname -m)" -o ~/bin/docker-compose
  - sudo chmod +x ~/bin/docker-compose
  - docker-compose --version

## Usage

1. Clone This Reposetory

    ```bash
    git clone https://github.com/Pradipbabar/MultiNodeTestLab.git
    cd MultiNodeTestLab
2. Generate SSH Key Pair:

    ```bash
    ssh-keygen -t rsa -b 4096
3. Update dockerfile and docker-compose.yml file accordingly
<br>

4. Build and Start the Container

    ```bash
    docker-compose up -d

5. Acess individual Containers
    `docker exec -it <conatiner name> bash`
    `ssh -i <private key> -p <port-number> root@localhost`


##Usage Scenarios
###Software Testing:
 Use this setup to test software that interacts with multiple servers in a distributed environment. Validate your software's behavior in various network conditions.

###Configuration Management Testing: 
Similar to tools like Ansible, Chef, and Puppet, use this setup to validate your own configuration management scripts or tools.

##Configuration

- The docker-compose.yml file defines the multi-node testing environment.
- Each node is isolated in its own Docker container.
- Modify the nodes/ directory to configure each node's software and services

