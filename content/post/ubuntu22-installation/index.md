---
title: Ubuntu 22.04 Installation and Configuration
description: Ubuntu 22.04 Workstation
slug: ubuntu22
date: 2025-10-26 00:00:00+0000
image: cover.jpg
categories:
    - Tutorial
tags:
    - ubuntu
weight:       # You can add weight to some posts to override the default sorting (date descending)
---

## 一、安装Ubuntu系统

### 1.1 制作启动U盘

1. [清华镜像网站](https://mirrors.tuna.tsinghua.edu.cn/)下载ubuntu-22.04.4-desktop-amd64.iso
2. [Rufus](https://rufus.ie/zh/#google_vignette)软件制作Ubuntu启动盘
    
    ![image.png](attachment:0176e570-3a9a-4308-a213-1746163242a7:image.png)
    
3. 磁盘分区：磁盘管理压缩分区

### 1.2 分区配置

| 分区 | 大小 (MB) | 分区类型 | 文件系统 | 挂载点 | 说明 |
| --- | --- | --- | --- | --- | --- |
| /dev/sda1 | 2,000 | 主分区 | FAT32 | /boot/efi | EFI 系统分区，存储 UEFI 启动文件 |
| /dev/sda2 | 2,000 | 主分区 | ext4 | /boot | 存储内核和启动文件，独立分区便于维护 |
| /dev/sda3 | 32,000 | 主分区 | swap | swap | 交换分区，支持 32GB 内存休眠 |
| /dev/sda4 | 256,000 | 主分区 | ext4 | / | 根目录，存储系统文件和软件 |
| /dev/sda5 | 708,000 | 逻辑分区 | ext4 | /home | 用户数据分区，占用剩余空间 |

## 二、黑屏问题解决

### 2.1 安装之前黑屏

1. 安装时，先选择" try or install ubuntu", 此时不要按enter，按"e"进入编辑模式；
2. 进入命令行模式, 找到 quiet splash，用nomodeset替换“- - -”，然后按F10启动系统，就可以进入桌面了

### 安装完成重启之后黑屏

1. 重启电脑；
2. 选择"Advanced options for Ubuntu"打开Ubuntu的高级选项；
3. 选择"recovery mode"恢复模式进入；
4. 选择"Drop to root shell prompt"，打开root shell 命令行页面；
5. 命令行中输入"sudo vi /etc/default/grub"修改grub文件；
6. 修改grub文件内容；
    
    ```bash
    1.输入i进入编辑模式，通过键盘的上下左右按键来移动光标，再编辑文本。
    2.将GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"修改为GRUB_CMDLINE_LINUX_DEFAULT="quiet splash nomodeset"。
    3.点击Esc退出编辑模式，再输入:wq保存grub文件。
    ```
    
7. 更新文件并重启；
    
    ```bash
    1.先sudo update-grub更新引导程序的配置。
     
    2.再执行reboot重启Ubuntu。
    ```
    
8. 等待重启，即可成功进入Ubuntu。

## 三、显卡驱动安装

## 四、WIFI驱动安装

## 五、软件安装

### 输入法配置

## 六、ROS2 安装

## 七、CUDA、Pytorch、conda安装

## 八、Isaac Sim安装

## 九、Isaac Lab安装
