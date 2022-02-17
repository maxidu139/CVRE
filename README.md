# ORB-SLAM3
The raw address:
https://github.com/UZ-SLAMLab/ORB_SLAM3

## Update to V1.0

Examples Monocular/Monocular-Inertial is available

### V1.0, December 22th, 2021
**Authors:** Carlos Campos, Richard Elvira, Juan J. Gómez Rodríguez, [José M. M. Montiel](http://webdiis.unizar.es/~josemari/), [Juan D. Tardos](http://webdiis.unizar.es/~jdtardos/).

The [Changelog](https://github.com/UZ-SLAMLab/ORB_SLAM3/blob/master/Changelog.md) describes the features of each version.

ORB-SLAM3 is the first real-time SLAM library able to perform **Visual, Visual-Inertial and Multi-Map SLAM** with **monocular, stereo and RGB-D** cameras, using **pin-hole and fisheye** lens models. In all sensor configurations, ORB-SLAM3 is as robust as the best systems available in the literature, and significantly more accurate.

We provide examples to run ORB-SLAM3 in the [EuRoC dataset](http://projects.asl.ethz.ch/datasets/doku.php?id=kmavvisualinertialdatasets) using stereo or monocular, with or without IMU, and in the [TUM-VI dataset](https://vision.in.tum.de/data/datasets/visual-inertial-dataset) using fisheye stereo or monocular, with or without IMU. Videos of some example executions can be found at [ORB-SLAM3 channel](https://www.youtube.com/channel/UCXVt-kXG6T95Z4tVaYlU80Q).

This software is based on [ORB-SLAM2](https://github.com/raulmur/ORB_SLAM2) developed by [Raul Mur-Artal](http://webdiis.unizar.es/~raulmur/), [Juan D. Tardos](http://webdiis.unizar.es/~jdtardos/), [J. M. M. Montiel](http://webdiis.unizar.es/~josemari/) and [Dorian Galvez-Lopez](http://doriangalvez.com/) ([DBoW2](https://github.com/dorian3d/DBoW2)).

<a href="https://youtu.be/HyLNq-98LRo" target="_blank"><img src="https://img.youtube.com/vi/HyLNq-98LRo/0.jpg"
alt="ORB-SLAM3" width="240" height="180" border="10" /></a>

# Intructions to Install (solved compile and dependencies problems)

## Libraries and Dependencies (*please follow instructions step by step.*)

### Git :
```shell script
    sudo apt install git
```

### C++ :
```shell script
    sudo apt install g++
    sudo apt install build-essential
```

### Libraries :
```shell script
    sudo add-apt-repository "deb http://security.ubuntu.com/ubuntu xenial-security main"
    sudo apt update
    sudo apt-get install cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev
    sudo apt-get install python-dev python-numpy libtbb2 libtbb-dev libjpeg-dev libpng-dev libtiff-dev libdc1394-22-dev libjasper-dev
    sudo apt-get install libglew-dev libboost-all-dev libssl-dev
    sudo apt install libeigen3-dev
```

### OpenCV :
```shell script
    cd ~
    mkdir Dev && cd Dev
    git clone https://github.com/opencv/opencv.git
    cd opencv
    git checkout 4.4.0
```

#### Add the next lines in the file : modules/videoio/src/cap_ffmpeg_impl.hpp 

  #define AV_CODEC_FLAG_GLOBAL_HEADER (1 << 22)

  #define CODEC_FLAG_GLOBAL_HEADER AV_CODEC_FLAG_GLOBAL_HEADER

  #define AVFMT_RAWPICTURE 0x0020

```shell script
    mkdir build
    cd build
    cmake -D CMAKE_BUILD_TYPE=Release -D WITH_CUDA=OFF -D CMAKE_INSTALL_PREFIX=/usr/local ..
    make -j 3
    sudo make install
```

### Eigen 3.2.10 :

#### Descargar .tar.bz2 de : https://eigen.tuxfamily.org/index.php?title=Main_Page
```shell script
    tar -xvf eigen3.2.10.tar.bz2
    cd eigen3.2.10
    mkdir build && cd build
    cmake ..
    make
    sudo make install

```










