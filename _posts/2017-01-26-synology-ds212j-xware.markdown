---
layout: post
title: "群晖 Synology DS212j 安装迅雷远程下载 xware"
date: "2017-01-26 20:21:29 +0800"
---


## 安装过程

群晖 Synology DS212j 安装迅雷远程下载 Xware。

```bash
# 参考链接下载对应型号的安装包

# 复制安装包
scp Xware1.0.31_armel_v5te_glibc.zip $nas:/tmp

# 准备安装目录, @ 开头不会出现在 NAS 共享目录中
sudo mkdir /volume1/@xware
cd /volume1/@xware

# 解压
mv /tmp/Xware1.0.31_armel_v5te_glibc.zip  ./
7z -x Xware1.0.31_armel_v5te_glibc.zip
rm Xware1.0.31_armel_v5te_glibc.zip

# mount xware 安装目录到 NAS 的一个共享目录中
# 否则提示 "存储空间不足" 或者 "存储路径错误#205" 或者 "没有检测到外接存储设备"
sudo mount --bind /volume1/@xware /volume1/file/xware

# 启动程序
/volume1/@xware/portal

# 显示一个 code， 登录迅雷远程进行绑定
# THE ACTIVE CODE IS: 15MCD2

```

## 开机启动

新建计划任务

```bash
sudo mount --bind /volume1/@xware /volume1/file/xware
/volume1/@xware/portal
```
 
# links 

- http://www.hkepc.com/forum/viewthread.php?fid=219&tid=2190059
- http://luyou.xunlei.com/forum.php?mod=attachment&aid=MjUxNDB8ZWE2M2E0Zjl8MTQzMDMxODc3OXw5OTk3M3wxMjU0NQ%3D%3D
- http://g.xunlei.com/thread-14788-1-1.html

 