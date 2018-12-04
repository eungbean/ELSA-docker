# Docker: python-opencv-ffmpeg(-cuda)

Repository for clean Dockerfile containing ffmpeg, opencv3 and python2/3, based on Ubuntu 16.04 LTS.

## Tags

* `:py3` Python 3.5, OpenCV 3.4.2, ffmpeg  (not av. yet)
* `:py3-cuda` Python 3.5, OpenCV 3.4.2, ffmpeg with CUDA 8.0 support


## Build

First you need to install docker on your local computer, see following [tutorial](https://docs.docker.com/install/linux/docker-ce/ubuntu/#set-up-the-repository). Note, for running the docker properly you have be logged as superuser otherwise you will face many partial issues which sometimes does not make much sense.

Use already build image from DockerHub which is significantly faster. it basically download the already build image.
``` bash
docker pull eungbean/elsa
```

Other option is building it on your own, note it takes lots of time, be prepared.
``` bash
git clone <git-repository>
cd docker_python-opencv-ffmpeg
docker image build -t eungbean/elsa -f Dockerfile-py3-cuda .
```
To build other versions, select different Dockerfile.


## Usage

Image has OpenCV3, python2.7/3.5 and ffmpeg ready to use. Example:

``` bash
docker run -rm -it \
-v $PWD:/srv eungbean/elsa \
>>> import cv2; cv2.VideoCapture(0).read()

# truncated for transparency
(True, array([[[ 0, 43, 37], ...]], dtype=uint8))
```