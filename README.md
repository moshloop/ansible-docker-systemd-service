##  moshloop.systemd-docker-service
 [![Build Status](https://travis-ci.org/moshloop/ansible-docker-systemd-service.svg?branch=master)](https://travis-ci.org/moshloop/ansible-docker-systemd-service)

An ansible role that runs a container using docker as a systemd service

### Arguments

| Argument       | Default              | Description |
| -------------- | -------------------- | ----------- |
| **image**        | [Required]           | Docker image to run  |
| **service** | [Required]       | The name of the systemd service |
| env     |                      | A dictionary of environment variables to pass through |
| docker_args |                      | Additional arguments to the docker client |
| args |                   | Additional arguments to the container |

### Example

```yaml
---
- hosts: localhost
  remote_user: root
  roles:
    - moshloop.systemd
  tasks:
    - include_role: name=../..
      vars:
        image: nginx
        service: nginx
        env:
          DOMAIN: localhost.com
```

