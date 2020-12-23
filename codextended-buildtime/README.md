# CoDExtended Buildtime Image

This Dockerfile can be used to build a Docker image that has all dependencies 
included to compile the [CoDExtended library](https://github.com/riicchhaarrd/CoDExtended).

Since the game is from 2003, the image is based on an i386 debian buster.

## Why?
Because Docker, that's why. You don't wanna pollute your brand new freaking fast x64 machine with ancient i386 libs.

## Quickstart
```
user@host: docker build -t tag:name .
user@host: docker run -it tag:name

root@5fe0a93773da:/opt/src# cd src
root@5fe0a93773da:/opt/src/src# ./build.sh    # see build-script parameters
```