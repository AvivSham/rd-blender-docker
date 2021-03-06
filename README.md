<div align="center">
  <h1>Blender in Docker</h1>
  <img width="500" src="./cover.png" />
  <p>A collection of Docker containers for running Blender headless or distributed ✨</p>
  <img alt="Python version" src="https://img.shields.io/badge/python-3.6-blue.svg" />
  <img alt="License" src="https://img.shields.io/badge/License-Apache%202.0-yellow.svg" />
  <a href="https://travis-ci.org/nytimes/rd-blender-docker"><img alt="Build status" src="https://travis-ci.org/nytimes/rd-blender-docker.svg?branch=master"></a><br/>
  •
    <a href="#getting-started">Getting Started</a> 📝
    •
    <a href="#docker-tags">Docker tags</a> 🏷️
    •
    <a href="#contributing">Contributing</a> 🛠
    •
    <a href="https://hub.docker.com/r/nytimes/blender">Docker Hub</a> 🐋
</div>

## Getting started
The images in this repository are autogenerated by running the `generate.py` script. The script uses `manifest.json` image definitions to define different versions and capabilities.
### If you just want to use one of the images in your Dockerfile
It should look like something like
```docker
FROM nytimes/blender:latest
```
For all tags available see [Docker tags](#docker-tags) or visit the [Docker Hub repository](https://hub.docker.com/r/nytimes/blender)

> If you are running a GPU image make sure you [follow and setup Nvidia Container Toolkit](https://github.com/NVIDIA/nvidia-docker)

## Docker tags
- `nytimes/blender:latest` - Latest GPU image with latest Blender version
### 2.82
- `nytimes/blender:2.82-cpu-ubuntu18.04`
- `nytimes/blender:2.82-gpu-ubuntu18.04`
### 2.81
- `nytimes/blender:2.81-cpu-ubuntu18.04`
- `nytimes/blender:2.81-gpu-ubuntu18.04`
### 2.80:
- `nytimes/blender:2.80-cpu-ubuntu18.04`
- `nytimes/blender:2.80-gpu-ubuntu18.04`

## Contributing
To contribute a new image make sure you:
- Add the image definition in the `manifest.json`
- Add the image to this README in the [Docker tags](#docker-tags) section
- PR your change and if everything is builds we will deploy it Docker Hub

## Running Blender with GUI on container
(tested on linux system)
After pulling the desired image you need to run container with the following command:

`docker run --ipc=host -it --net=host --env="DISPLAY" --volume="$HOME/.Xauthority:/root/.Xauthority:rw"  <IMAGE NAME>`

If you want to use GPU support as well please setup Nvidia's container toolkit and just replace `docker` 
with `nvidia-docker` for the previous command. 

> This repository is maintained by the Research & Development team at The New York Times and is provided as-is for your own use. For more information about R&D at the Times visit [rd.nytimes.com](https://rd.nytimes.com)