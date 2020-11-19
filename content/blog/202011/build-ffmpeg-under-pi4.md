---
title: "在Pi4上编译ffmpeg支持硬件编解码以及测试和使用方法"
date: 2020-11-19T15:27:31+08:00
draft: true
---

由于某些原因，需要在raspberry pi 4上编译最新版本ffmpeg，下面是方法以及测试方案。


## 编译准备

```
sudo apt update
sudo apt upgrade
```

## 安装必要的工具和库

```
sudo apt install build-essential yasm pkg-config libx264-dev
```

## 下载源代码并编译

```
# 下载并解压
wget http://ffmpeg.org/releases/ffmpeg-snapshot-git.tar.bz2
tar jxvf ffmpeg-snapshot-git.tar.bz2
cd ffmpeg

# 切换到明确的tag并创建分支
git checkout tags/n4.3.1 -b b4.3.1

./configure --enable-gpl --enable-libx264 --enable-mmal --enable-omx --enable-omx-rpi

## pi4 2G上大约需要14分钟左右，请注意cpu散热
make -j4

sudo make install
```



## 测试rtsp h.265的cpu解码，并每5s保存一张图片

## 测试rtsp h.265硬解，并每5s保存一张图片



## 参考

[Compile FFmpeg for Ubuntu, Debian, or Mint](https://trac.ffmpeg.org/wiki/CompilationGuide/Ubuntu)

[Hardware Encoding with the Raspberry Pi](https://www.redhenlab.org/home/the-cognitive-core-research-topics-in-red-hen/the-barnyard/hardware-encoding-with-the-raspberry-pi)

