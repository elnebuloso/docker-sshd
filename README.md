<img src="https://raw.githubusercontent.com/elnebuloso/docker-sshd/master/logo.png" width="100%"/>

# docker-sshd

![Release](https://github.com/elnebuloso/docker-sshd/workflows/Release/badge.svg)
[![Docker Pulls](https://img.shields.io/docker/pulls/elnebuloso/sshd.svg)](https://hub.docker.com/r/elnebuloso/sshd)
[![GitHub](https://img.shields.io/github/license/elnebuloso/docker-ansible.svg)](https://github.com/elnebuloso/docker-sshd)

Dockerized SSH Service Containers

## github

- https://github.com/elnebuloso/docker-sshd

## docker

- https://hub.docker.com/r/elnebuloso/sshd
- https://hub.docker.com/r/elnebuloso/sshd/tags?page=1&ordering=last_updated

## usage

- for testing ssh connections against dockerized hosts
- e.g. ansible role testing

## examples

### dockerized ansible role testing

#### docker-compose.yml

```
version: "2"

services:
  ansible:
    image: elnebuloso/ansible:2-ubuntu18
    entrypoint: /usr/bin/yes
    volumes:
      - .:/etc/ansible/roles/role:ro
    environment:
      ANSIBLE_HOST_KEY_CHECKING: "false"

  ubuntu14:
    image: elnebuloso/sshd:ubuntu14

  ubuntu16:
    image: elnebuloso/sshd:ubuntu16

  ubuntu18:
    image: elnebuloso/sshd:ubuntu18

  debian7:
    image: elnebuloso/sshd:debian7

  debian8:
    image: elnebuloso/sshd:debian8

  debian9:
    image: elnebuloso/sshd:debian9
    
  centos6:
    image: elnebuloso/sshd:centos6

  centos7:
    image: elnebuloso/sshd:centos7
```

#### run ansible playbook against hosts

```
docker-compose exec ansible ansible-playbook -i "ubuntu14,ubuntu16,ubuntu18,debian7,debian8,debian9,centos6,centos7" /etc/ansible/roles/role/tests/test.yml
```