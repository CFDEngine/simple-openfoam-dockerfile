# Simple OpenFOAM Dockerfile

This repository contains 2 example Dockerfiles which can be used as inspiration to build your own custom OpenFOAM Docker images.

I've included versions for OpenFOAM.com & OpenFOAM.org releases - both based on Ubuntu Focal (20.04 LTS), using the respective pre-compiled binaries.

The OpenFOAM.com version installs the minimal OpenFOAM package plus the tutorials.

The OpenFOAM.org version is installed _without_ ParaView to _slightly_ reduce the image size.

## Build Instructions

To build an image locally, download the Dockerfile of interest & open the location of the file in a terminal.

The following command will build a local Docker image called `myopenfoam:v8.0`

```shell
docker image build -t myopenfoam:v8.0 .

```

## Usage

Once built, you can launch your custom OpenFOAM Docker image using the following command:

```shell
docker container run -ti --rm -v $PWD:/data -w /data myopenfoam:v8.0
```

Which will start an interactive session in your Docker container with your current working directory on your local filesystem mounted as `/data` in your container. The container will be removed once you exit it.

These are just the briefest notes, for a deep-dive into using OpenFOAM with Docker see [the full article](https://www.cfdengine.com/blog/how-to-install-openfoam-anywhere-with-docker/).
