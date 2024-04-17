# Deployment using Docker

## Overview

The primary goal is to build and deploy a container with all the project needed packages in order to avoid installation issues or incompatibilities, this container will minimize the required time to start developing on the project.

## Getting Started

To build and deploy the container follow the steps below.

### Prerequisites

Ensure you have the following software and dependencies installed:

- [docker](https://docs.docker.com/engine/install/ubuntu/)
- \* [nvidia-container-toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html)

*\* Only if GPU is needed*

## Usage

1. Build the container:
    ```bash
    docker build -t lsy_drone_racing docker/
    ```

2. Deploy the container:
    ```bash
    docker run --gpus all --shm-size=16g -it -v .:/workdir lsy_drone_racing
    ```

The local files will be mount on `/wordir`, it allows to preserve the changes.