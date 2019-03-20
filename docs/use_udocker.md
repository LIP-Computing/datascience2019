---
title: Using udocker with available images
layout: default
---

# Using udocker with available images

[uDocker](https://github.com/indigo-dc/udocker) is a basic user tool to execute simple docker containers in user space without requiring root privileges. It doesn't require any package to be installed on most cases, since it only requires some basic tools.

First start to get uDocker from a mirror such as using the following command into your project directory:
```
curl https://download.ncg.ingrid.pt/webdav/udocker/udocker-1.1.3.tar.gz > ${PROJECT_HOME}/udocker.tar.gz
```

Replace `${PROJECT_HOME}` with the path to your project home directory.

Then setup uDocker environment going to your project directory and running the following commands:
```
cd ${PROJECT_HOME}/
tar xzvf udocker.tar.gz udocker
export UDOCKER_DIR=${PROJECT_HOME}/.udocker
./udocker install
```

Pull desired images from docker hub, selecting one of the tags available in [Docker Images page](./docker_images.html):
```
./udocker pull lipcomputing/data_science_school_2019:<tag>
```

Extract image to use with uDocker:
```
./udocker create --name=<name> lipcomputing/data_science_school_2019:<tag>
```

where \<name\> is the desired name you want for the container created from the selected image.

To start docker image with Jupiter notebook:
```
./udocker run -p 8888:8888 <name>
```

For more details about available commands and their options review the [uDocker user manual](https://github.com/indigo-dc/udocker/blob/master/doc/user_manual.md).

[back](./)
