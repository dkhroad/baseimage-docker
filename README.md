# A minimal Ubuntu (12.04) base image modified for Docker-friendliness 

Baseimage-docker is a special [Docker](http://www.docker.io) image that is configured for correct use within Docker containers. It is Ubuntu, plus modifications for Docker-friendliness. You can use it as a base for your own Docker images.

See the original Readme [Here](https://github.com/phusion/baseimage-docker)

This fork contains following changes for my personal use:

* Changes to  Ubuntu 12.04 as base image
* Allow runtime adding of SSH keys. The issue is described [here](https://github.com/phusion/baseimage-docker/issues/107)  
  and implemented [here](https://github.com/rfkrocktk/docker-baseimage/blob/develop/scripts/01_add_ssh_keys.sh)
  To add a ssh key at runtime, pass the SSH key in environment variable 
  while running your docker container like this: 
```
docker run --rm   -P -e SSH_KEYS="$(cat ~/.ssh/id_rsa.pub)" dkhroad/base:0.2
```


