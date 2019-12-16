[![License](http://img.shields.io/:license-apache-blue.svg?style=flat-square)](http://www.apache.org/licenses/LICENSE-2.0.html)
[![Build Status](https://travis-ci.org/LIP-Computing/ansible-role-nvidia.svg?branch=master)](https://travis-ci.org/LIP-Computing/ansible-role-nvidia)

# Ansible role to install nvidiadrivers

The role deploys the NVIDIA driver in GPU machines, these can be
baremetal or VMs.

Supported Operating systems are Centos7 and Ubuntu 18.04.

## Requirements

The machine or VM should have a NVIDIA GPU, can be checked with:

    lspci |grep NVIDIA

## Install role

The role can be installed directly from github:

    ansible-galaxy install git+https://github.com/LIP-Computing/ansible-role-nvidia.git

From ansible Galaxy:

    ansible-galaxy install -f LIP-Computing.ansible-role-nvidia

## Role Variables

These variables should be changed depending on your type of machine.
Specifically the driver version may need to be set:

* `nvidia_driver_version: 440.33.01` -  NVIDIA driver version, check the default value.
in defaults/main.yml as well as a list of valid versions.
* `kmod_install: true` - install kernel module, only for baremetal and VMs.
* `dev_create: false` - run a script to create devices in the host, only if `kmod_install: true`
* `nv_persistence: true` - Set nvidia-smi --persistence-mode=1.

The variable kmod_install enables the installation (or not) of the nvidia
kernel module. In the case of docker images the value should be **false**,
while in the case of baremetal or VMs it should be **true**.

These variables have pre-configured values that should not be needed to change:

* `base_url`: Base URL of NVIDIA download
* `nvidia_driver`: Filename of the NVIDIA driver, depends on the variable nvidia_driver_version
* `nvidia_url`: Full URL of the NVIDIA driver, depends on the variables base_url and nvidia_driver

## Example Playbook

Playbook example: deployment of driver version 440.33.01 on a VM

    - hosts: servers
      roles:
        - { role: LIP-Computing.ansible-role-nvidia, nvidia_driver_version: 40.33.01, kmod_install: true }

## License

Apache v2

## Author Information

* Mario David: <mariojmdavid@gmail.com>
* LIP Lisbon: <http://www.lip.pt>
* Projects:
  * Indigo DataCloud: <https://www.indigo-datacloud.eu/>
  * DEEP Hybrid Datacloud: <https://deep-hybrid-datacloud.eu/>
  * EOSC Synergy: <https://www.eosc-synergy.eu/>
