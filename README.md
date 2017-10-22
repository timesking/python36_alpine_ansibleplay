# python36_alpine_ansibleplay

Dockerfile for Python3.6.3 and ansible-play based on alpine


Docker based on python:3.6.3-alpine

I just merged some codes from:

- https://github.com/yikaus/docker-alpine-bash
- https://medium.com/@tech_phil/running-ansible-inside-docker-550d3bb2bdff
- https://github.com/philm/ansible_playbook

You can run it by:

```
# docker run --rm -it -v $(pwd):/ansible/playbooks philm/ansible_playbook site.yml
```

Or if you require some special ssh key for ansible playbook runnning:
```
docker run --rm -it \
    -v ~/.ssh/id_rsa:/root/.ssh/id_rsa \
    -v ~/.ssh/id_rsa.pub:/root/.ssh/id_rsa.pub \
    -v $(pwd):/ansible/playbooks \
    philm/ansible_playbook site.yml
```