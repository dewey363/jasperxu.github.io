---
title: Win10 Samba连接不上问题
linkname: win10-samba-can-not-connection
date: 2019-07-05
updated: 2019-07-05
categories:
- 记录
tags:
- system
- windows
---

更新到Win10 1709之后的版本后Samba会连接不上。需要做如下设置：
### 在Windows功能中启用如下功能
```
SMB 1.0/CIFS 文件共享支持
    SMB 1.0/CIFS 服务器
    SMB 1.0/CIFS 客户端
SMB 直通
```

### 在注册表regedit中加入或修改如下键
```
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\LanmanWorkstation\Parameters\AllowInsecureGuestAuth

DWORD (32位) 值
设置为1
```

### 重启电脑，即可！

<!-- more -->