[![License](http://img.shields.io/:license-apache-blue.svg?style=flat-square)](http://www.apache.org/licenses/LICENSE-2.0.html)
[![](https://images.microbadger.com/badges/image/lipcomputing/nvidia-ubuntu16.04.svg)](http://microbadger.com/images/lipcomputing/nvidia-ubuntu16.04 "Get your own image badge on microbadger.com")

# nvidia-ubuntu16.04

Docker image with NVIDIA driver.

## Installed packages

Base:
- Ansible

Image specific:
- NVIDIA driver

## Build

```bash
docker build --rm -t nvidia-ubuntu16.04 .
```

## Usage

```bash
$ docker run -it
$ docker run \
    --device=/dev/nvidia0:/dev/nvidia0 \
    --device=/dev/nvidiactl:/dev/nvidiactl \
    --device=/dev/nvidia-uvm:/dev/nvidia-uvm \
    -it \
    nvidia-ubuntu16.04 /bin/bash
```

License
-------

Apache v2

Author Information
------------------

Mario David: <mariojmdavid@gmail.com>

LIP Lisbon: http://www.lip.pt

Indigo DataCloud: https://www.indigo-datacloud.eu/
