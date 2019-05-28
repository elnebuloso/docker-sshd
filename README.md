# docker-sshd

Dockerized SSH service

## example usages for this images

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
```

```
docker-compose exec ansible ansible-playbook -i "ubuntu14,ubuntu16,ubuntu18,debian7,debian8,debian9" /etc/ansible/roles/role/tests/test.yml
```