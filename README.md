##  moshloop.systemd_docker_service
 [![Build Status](https://travis-ci.org/moshloop/ansible-docker-systemd-service.svg?branch=master)](https://travis-ci.org/moshloop/ansible-docker-systemd-service)

An ansible role that runs a container using docker as a systemd service

### Container Arguments

| Argument       | Default              | Description |
| -------------- | -------------------- | ----------- |
| **image**        | [Required]           | Docker image to run  |
| **service** | [Required]       | The name of the systemd service |
| env     |                      | A dictionary of environment variables to pass through |
| docker_args |                      | Additional arguments to the docker client e.g. `-p 8080:8080` |
| docker_opts | | Additional options to the docker client e.g. `-H unix:///tmp/var/run/docker.sock` |
| args |                   | Additional arguments to the container |
| volumes |                |                                       |
| ports |                |                                       |
| links |                |                                       |


### Example

```yaml
---
- hosts: localhost
  roles:
    - moshloop.systemd
  tasks:
    - include_role: name=moshloop.docker_systemd_service
      vars:
      	containers:
         - image: nginx
           service: nginx
           env:
             DOMAIN: localhost.com
         - image: nginx
           service: nginx2
           docker_args: -p 8080:80

```

