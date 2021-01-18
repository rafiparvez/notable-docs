---
tags: [cuda, machine-learning]
title: Setting Up Development Environment for Machine Learning
created: '2020-05-23T17:41:38.481Z'
modified: '2021-01-17T20:15:20.820Z'
---

# Setting Up Development Environment for Machine Learning

## Install Graphics Drivers
Check if drivers are installed by running `nvidia-smi`.  
If not installed, installed Nvidia graphics drivers using these commands:  
```
# purge any existing pkgs
sudo apt-get purge nvidia-*
```

```
# check drivers recommendations

$ ubuntu-drivers devices
== /sys/devices/pci0000:00/0000:00:01.0/0000:01:00.0 ==
modalias : pci:v000010DEd00001E07sv00001458sd000037A9bc03sc00i00
vendor   : NVIDIA Corporation
model    : TU102 [GeForce RTX 2080 Ti Rev. A]
driver   : nvidia-driver-440 - distro non-free recommended
driver   : nvidia-driver-435 - distro non-free
driver   : xserver-xorg-video-nouveau - distro free builtin

```

```
# install drivers and restart
sudo apt update
sudo apt upgrade

sudo apt install nvidia-driver-440
sudo apt install nvidia-settings

sudo reboot
```  

## Install Cuda Toolkit

From Nvidia's webside
```
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/cuda-ubuntu2004.pin
sudo mv cuda-ubuntu2004.pin /etc/apt/preferences.d/cuda-repository-pin-600
wget https://developer.download.nvidia.com/compute/cuda/11.2.0/local_installers/cuda-repo-ubuntu2004-11-2-local_11.2.0-460.27.04-1_amd64.deb
sudo dpkg -i cuda-repo-ubuntu2004-11-2-local_11.2.0-460.27.04-1_amd64.deb
sudo apt-key add /var/cuda-repo-ubuntu2004-11-2-local/7fa2af80.pub
sudo apt-get update
sudo apt-get -y install cuda
```
Then add following lines to `~/.bashrc`  
```
export CUDA_HOME=/usr/local/cuda
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda/lib64:/usr/local/cuda/extras/CUPTI/lib64
export PATH=$PATH:$CUDA_HOME/bin
```
  
Alternatively, you can install the package as follows
```
sudo apt update
sudo apt install nvidia-cuda-toolkit
```
### check cuda toolkit version
```
$ nvcc --version
  nvcc: NVIDIA (R) Cuda compiler driver
  Copyright (c) 2005-2020 NVIDIA Corporation
  Built on Mon_Nov_30_19:08:53_PST_2020
  Cuda compilation tools, release 11.2, V11.2.67
  Build cuda_11.2.r11.2/compiler.29373293_0
```

## Install CuDNN Libraries

CuDNN is a GPU-accelerated library, which has highly tuned implementations for standard routines such as forward and backward convolution, pooling, normalization, and activation layers.
You need to join Nvidia developer membership and download the library from the link 
https://developer.nvidia.com/rdp/cudnn-download. Once the package is downloaded, run these commands  
```
# Install the runtime library
$ sudo dpkg -i libcudnn8_8.0.5.39-1+cuda11.1_amd64.deb

# Install the developer library
$ sudo dpkg -i libcudnn8-dev_8.0.5.39-1+cuda11.1_amd64.deb

# Install the code samples and dev doc
$ sudo dpkg -i libcudnn8-samples_8.0.5.39-1+cuda11.1_amd64.deb
```
## Install Anaconda  

```
# install extended dependencies to use GUI tools
$ sudo apt-get install libgl1-mesa-glx libegl1-mesa libxrandr2 libxrandr2 libxss1 libxcursor1 libxcomposite1 libasound2 libxi6 libxtst6

# download and install library
$ wget "https://repo.anaconda.com/archive/Anaconda3-2020.02-Linux-x86_64.sh" -O conda3.sh
$ chmod +x conda3.sh
$ bash conda3.sh -u -b
```














