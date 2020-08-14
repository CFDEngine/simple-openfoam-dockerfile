# Simple OpenFOAM Dockerfile

This repository contains 2 example Dockerfiles which can be used as inspiration to build your own custom OpenFOAM Docker images.

I've included versions for OpenFOAM.com & OpenFOAM.org releases - both based on Ubuntu Focal (20.04 LTS), using the respective pre-compiled binaries.

The OpenFOAM.com version uses the minimal OpenFOAM package plus the tutorials.

The OpenFOAM.org version is installed _without_ ParaView to _slightly_ reduce the size.

For further details see [Install OpenFOAM anywhere with Docker](https://www.cfdengine.com/blog/how-to-install-openfoam-anywhere-with-docker/)
