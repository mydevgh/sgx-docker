# SGX DOCKER PATCHES

This is a Git repository for Intel SGX applications using Docker Containers. The Intel(R) Software Guard Extensions (Intel(R) SGX) is an Intel technology for application developers seeking to protect select code and data from disclosure or modification.

The Linux SGX software stack is comprised of the SGX driver, the SGX SDK, and the SGX Platform Software. The SGX SDK and SGX PSW are hosted in the [linux-sgx](https://github.com/01org/linux-sgx) project.

The [linux-sgx-driver](https://github.com/01org/linux-sgx-driver) project hosts the out-of-tree driver for the Linux SGX software stack, which will be used until the driver upstreaming process is complete. 

**Running SGX application requires installing SGX driver and SGX PSW/SDK to host.

## Download Docker Image

1 - Download a docker image:

```bash
$ docker pull aminueza/docker-sgx
```

## Download Dockerfile

```bash
$ git clone https://github.com/aminueza/sgx-docker.git
$ rm -rf 00*.patch
```

## Build a new docker image

2 - Build a new image:

```bash
$ docker build -t <image name> <destination-dir>
```

i.e: "docker build -t app-sgx ."

3 - Run a new image:

```bash
$ docker run --device=/dev/isgx -it <image name>
```

i.e: "docker run --device=/dev/isgx -it app-sgx"

*or start an interactive bash session:

```bash
$ docker run --device=/dev/isgx -it <image name> /bin/bash
```
