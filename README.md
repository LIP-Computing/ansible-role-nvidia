[![License](http://img.shields.io/:license-apache-blue.svg?style=flat-square)](http://www.apache.org/licenses/LICENSE-2.0.html)
[![Build Status](https://travis-ci.org/LIP-Computing/ansible-role-nvidia.svg?branch=master)](https://travis-ci.org/LIP-Computing/ansible-role-nvidia)

ansible-role-nvidia
===================

The role deploys the NVIDIA driver in GPU machines, these can be
baremetal, VMs or Dockers.

Supported Operating systems are Centos7 and Ubuntu 16.04.

Requirements
------------

The machine, VM or docker should have a NVIDIA GPU, can be checked with:

```
lspci |grep NVIDIA
```

Role Variables
--------------

These variables should be changed depending on your type of machine.
Specifically the driver version may need to be set if you are using
docker containers where the version on the docker image has to match the
version on the host machine:

* nvidia_driver_version: NVIDIA driver version, check the default value
in defaults/main.yml as well as a list of valid versions 
* kmod_install: true|false

The variable kmod_install enables the installation (or not) of the nvidia
kernel module. In the case of docker images the value should be **false**,
while in the case of baremetal or VMs it should be **true**.

These variables have pre-configured values that should not be needed to change:

* base_url: Base URL of NVIDIA download
* nvidia_driver: Filename of the NVIDIA driver, depends on the variable nvidia_driver_version
* nvidia_url: Full URL of the NVIDIA driver, depends on the variables base_url and nvidia_driver

Example Playbook
----------------

Playbook example: deployment of driver version 352.93 on a VM

    - hosts: servers
      roles:
        - { role: LIP-Computing.ansible-role-nvidia, nvidia_driver_version: 352.93, kmod_install: true }

An example of deployment of driver 352.99 on a docker container:

    - hosts: servers
      roles:
        - { role: LIP-Computing.ansible-role-nvidia, nvidia_driver_version: 352.99, kmod_install: false }

License
-------

Apache v2

Author Information
------------------

Mario David: <mariojmdavid@gmail.com>

LIP Lisbon: http://www.lip.pt

Indigo DataCloud: https://www.indigo-datacloud.eu/
