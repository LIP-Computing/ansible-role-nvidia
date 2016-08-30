[![License](http://img.shields.io/:license-apache-blue.svg?style=flat-square)](http://www.apache.org/licenses/LICENSE-2.0.html)

# nvidia-centos7

Docker image with NVIDIA driver.

## Installed packages

Base:
- Ansible

Image specific:
- NVIDIA driver

## Build

```bash
docker build --rm -t nvidia-centos7 .
```

## Usage

```bash
$ docker run -it nvidia-centos7 /bin/bash
```

License
-------

Apache v2

Author Information
------------------

Mario David: <mariojmdavid@gmail.com>

LIP Lisbon: http://www.lip.pt

Indigo DataCloud: https://www.indigo-datacloud.eu/
