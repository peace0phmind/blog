---
title: "AGX添加NVME以及从NVME盘启动"
date: 2020-10-22T16:51:33+08:00
draft: true
---

AGX出厂自带32G EMMC，并自带Ubuntu 18.04 + JetPack 4.4。本文对EMMC进行了磁盘读写的测试，并且对AGX进行改装，f分别测试加装了海康的1T nvme ssd硬盘和SAMSUNG 1T nvme ssd，并进行了对比测试。最后简单介绍了了如何将AGX的默认启动方式修改为从nvme的ssd启动。

## 磁盘读写性能测试方式

使用linux下的dd进行磁盘读写性能测试。

1.测试磁盘写速度
```
sync; dd if=/dev/zero of=tempfile bs=1M count=1024; sync
```

2.测试磁盘读速度
```
dd if=tempfile of=/dev/null bs=1M count=1024
```

3.清理读缓存
```
sudo /sbin/sysctl -w vm.drop_caches=3
```

## emmc性能测试

### 下图为emmc写盘和覆盖写
1. emmc写盘1.4 GB/s(实际测试结果输出后，该民令并没有立即结束，所以这里的数据并不能用于参考)
1. emmc覆盖写的速度大概在119 MB/s
![emmc写盘和覆盖写](/blog/img/202010/add-nvme-ssd/emmc-write-rewrite.png)

### 下图为emmc缓存读和直接读的速度
1. emmc缓存读的速度很高，在7.7GB/s左右
1. emmc直接读取的速度很低，在307 MB/s左右

![emmc缓存读和直接读的速度](/blog/img/202010/add-nvme-ssd/emmc-cacheread-directread.png)

## SamSung 1T SSD性能测试

### 下图为SamSung写盘和覆盖写
1. SamSung写盘1.3 GB/s
1. SamSung覆盖写的速度大概在897 MB/s
![SamSung写盘和覆盖写](/blog/img/202010/add-nvme-ssd/samsung-write-rewrite.png)

### 下图为SamSung缓存读和直接读的速度
1. SamSung缓存读的速度很高，在7.1GB/s左右
1. SamSung直接读取的速度很低，在1.7 GB/s左右

![SamSung缓存读和直接读的速度](/blog/img/202010/add-nvme-ssd/samsung-cacheread-directread.png)

## HikVision 1T SSD性能测试

### 下图为HikVision写盘和覆盖写
1. HikVision写盘1.3 GB/s
1. HikVision覆盖写的速度大概在992 MB/s
![HikVision写盘和覆盖写](/blog/img/202010/add-nvme-ssd/HikVision-write-rewrite.jpg)

### 下图为HikVision缓存读和直接读的速度
1. HikVision缓存读的速度很高，在7.9GB/s左右
1.HikVision直接读取的速度很低，在1.6 GB/s左右

![HikVision缓存读和直接读的速度](/blog/img/202010/add-nvme-ssd/HikVision-cacheread-directread.jpg)

