# SETUP FOR JETSON NANO DEVELOPER TOOLKIT


## Get image to boot

### Xubuntu 20.04
Link img: https://github.com/Discombobulated88/Xubuntu-20.04-L4T-32.3.1/releases/download/v1.0/Xubuntu-20.04-l4t-r32.3.1.tar.tbz2
Link app: https://www.balena.io/etcher/

### Jetson Ubuntu 18.04
Link img: https://developer.download.nvidia.com/assets/embedded/downloads/jetson-nano-sd-card-image/r32.2-2019-07-17/jetson-nano-sd-r32.2-2019-07-16.zip
Link app: Win32DiskImager

## Update ubuntu

``` bash
sudo apt update
```

## Install CMAKE

```bash
sudo apt install cmake
sudo apt install cmake-gui cmake-qt-gui
```

## Install python package

```bash
sudo apt -y install libpython3-dev python3-numpy
```

## Install Qt5

```bash
sudo apt-get install qtbase5-dev
```

## Install another packages for c++ program

```bash
sudo apt -y install libcrypto++-dev 
sudo apt -y install libgoogle-glog-dev 
sudo apt -y install libgflags-dev
sudo apt -y install --no-install-recommends libboost-all-dev
```

## Install Jetson monitor

```bash
sudo -H pip3 install jetson-stats
```

## Run Jetson monitor

```bash
sudo -H json
```

## Build Jetson-inference

```bash
git clone --recursive https://github.com/dusty-nv/jetson-inference
cd jetson-inference
git submodule update --init
mkdir build
cd build
sudo cmake ..
```

## Compile and install Jetson-inference
```bash
sudo make
sudo make install
sudo ldconfig
```


## Install DeepStream SDK

```bash
sudo apt install \
    libssl1.0.0 \
    libgstreamer1.0-0 \
    gstreamer1.0-tools \
    gstreamer1.0-plugins-good \
    gstreamer1.0-plugins-bad \
    gstreamer1.0-plugins-ugly \
    gstreamer1.0-libav \
    libgstrtspserver-1.0-0 \
    libjansson4=2.11-1

sudo apt-get install librdkafka1=0.11.3-1build1

tar -xpvf deepstream_sdk_v4.0.2_jetson.tbz2
cd deepstream_sdk_v4.0.2_jetson
sudo tar -xvpf binaries.tbz2 -C /
sudo ./install.sh
sudo ldconfig

sudo apt-get install ./deepstream-4.0_4.0.2-1_arm64.deb

sudo nvpmodel -m 0 
sudo jetson_clocks
```

## Run Deepstream app

```bash
deepstream-app --help
```

## Install Dlib
```bash
sudo apt update
sudo apt-get install build-essential cmake
sudo apt-get install libgtk-3-dev
sudo apt-get install libboost-all-dev
sudo pip3 install dlib
```

## Install Qt4

```bash
sudo apt update
sudo apt-get install python3-pyqt4
```