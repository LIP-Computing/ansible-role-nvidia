[![License](http://img.shields.io/:license-apache-blue.svg?style=flat-square)](http://www.apache.org/licenses/LICENSE-2.0.html)
[![Build Status](https://travis-ci.org/LIP-Computing/ansible-role-nvidia.svg?branch=master)](https://travis-ci.org/LIP-Computing/ansible-role-nvidia)

ansible-role-nvidia
===================

The role deploys the NVIDIA driver in GPU machines, these can be
baremetal, VMs or Dockers

Requirements
------------

The machine, VM or docker should have a NVIDIA GPU, can be checked with:

```
lspci |grep NVIDIA
```

Role Variables
--------------

* nvidia_driver_version: 
* base_url: 
* nvidia_driver: 
* nvidia_url: 
* kmod_install: 

Example Playbook
----------------

Playbook example

    - hosts: servers
      roles:
         - ansible-role-nvidia

License
-------

Apache v2

Author Information
------------------

Mario David: <mariojmdavid@gmail.com>

LIP Lisbon: http://www.lip.pt

Indigo DataCloud: https://www.indigo-datacloud.eu/
