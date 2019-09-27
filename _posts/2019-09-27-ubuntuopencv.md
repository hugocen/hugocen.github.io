---
title: "如何在Ubuntu 18.04 中安裝 OpenCV"
date: 2019-09-27T18:10:22-00:00
categories:
  - Linux
tags:
  - linux
  - python
  - opencv
  - ubuntu
  - computer vision
---

在Ubuntu 18.04 中安裝 OpenCV 可參考以下指令  
```bash
cd ~
wget -O opencv.zip https://github.com/opencv/opencv/archive/3.4.4.zip
wget -O opencv_contrib.zip https://github.com/opencv/opencv_contrib/archive/3.4.4.zip
unzip opencv.zip
unzip opencv_contrib.zip
mv opencv-3.4.4 opencv
mv opencv_contrib-3.4.4 opencv_contrib
cd ~/opencv
mkdir build
cd build/

cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local -D INSTALL_PYTHON_EXAMPLES=ON -D INSTALL_C_EXAMPLES=OFF -D OPENCV_ENABLE_NONFREE=ON -D OPENCV_EXTRA_MODULES_PATH=~/opencv_contrib/modules -D PYTHON_EXECUTABLE=~/.virtualenvs/cv/bin/python -D BUILD_EXAMPLES=ON ..

make -j4
sudo make install
sudo ldconfig
ls /usr/local/python/cv2/python-3.6
cd /usr/local/python/cv2/python-3.6
sudo mv cv2.cpython-36m-x86_64-linux-gnu.so cv2.so
```