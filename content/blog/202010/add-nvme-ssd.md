---
title: "AGX改装"
date: 2020-10-22T16:51:33+08:00
draft: true
---

    AGX出厂自带32G EMMC，并自带Ubuntu 18.04 + JetPack 4.4。本文对EMMC进行了磁盘读写的测试，并且对AGX进行改装，加装了海康的1T nvme ssd硬盘，并进行了对比测试。最后简单介绍了以下如何将AGX的默认启动方式修改为从nvme的ssd启动。

    本文使用linux下的dd进行磁盘读写性能测试。首先介绍几个测试命令：

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
