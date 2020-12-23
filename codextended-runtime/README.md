# CoDExtended Runtime Image

This Dockerfile can be used to build a Docker image that has all dependencies 
included to run Call of Duty 1.1 Linux Dedicated Multiplayer Server extended by
the [CoDExtended library](https://github.com/riicchhaarrd/CoDExtended).

Since the game is from 2003, the image is based on an i386 debian buster.

## Why?
Because Docker, that's why. You don't wanna pollute your brand new freaking fast x64 machine with ancient i386 libs.

## What's missing
Port handling related to running multiple servers on same host machine. The server will send its port 
to the master-server. Since the containers and host ports are mapped, the ports could be different. 
The host port mapped to the container should be the same. Running multiple servers on same host
requires the servers var ```net_port``` to be adjusted.

## Gametype Zombies
As writing this in December 2020 this image works with [Zombies Mod](https://github.com/thecheeseman/zombies_v5_r13)
in version *Zombies v5 Revision 13.1.2*. Since this mod saves the players stats to files in 
```stats/players/``` folder, make sure you create this folder based in games root directory
that you mount to the containers ```/opt/codmp/``` location. Stats saving and loading will 
not work, if the ```/opt/codmp/stats/players/``` folder in the container does not exist.