[![License](http://img.shields.io/:license-apache-blue.svg?style=flat-square)](http://www.apache.org/licenses/LICENSE-2.0.html)
[![](https://images.microbadger.com/badges/image/lipcomputing/nvidia-centos7.svg)](http://microbadger.com/images/lipcomputing/nvidia-centos7 "Get your own image badge on microbadger.com")

# nvidia-centos7

Docker image with NVIDIA driver.

## Installed packages

Base:
- Ansible

Image specific:
- NVIDIA driver

The NVIDIA driver version is tagged in the docker image as follows

* TAG = nvdrv_352.93 : nvidia driver version 352.93
* TAG = nvdrv_352.99 : nvidia driver version 352.99

## Build

```bash
docker build --rm -t nvidia-centos7 .
```

## Usage

```bash
$ docker run \
    --device=/dev/nvidia0:/dev/nvidia0 \
    --device=/dev/nvidiactl:/dev/nvidiactl \
    --device=/dev/nvidia-uvm:/dev/nvidia-uvm \
    -it \
    nvidia-centos7 /bin/bash
```

License
-------

Apache v2

Author Information
------------------

Mario David: <mariojmdavid@gmail.com>

LIP Lisbon: http://www.lip.pt

Indigo DataCloud: https://www.indigo-datacloud.eu/
