++++++
title="Windows优化记录"
filename="windows_tweak"
date="2024-07-02T20:01:58"
tags=["优化", "Windows"]
category="Windows"
++++++

# Windows 优化记录

> Linux 虽好，但是我已经对这样学不到什么的折腾祛魅了。自从初一第一次在无人问津的图书馆角落找到一本09年出版的、有关 Ubuntu 的使用指南，过往的六年里只能算作一个 Linux 的使用者，而非一个研究者、生产者。
>
> 新电脑就 Windows 养老好了。只是失去了包管理器而已，我得到的则是桌面系统的稳定性和日常的游戏摸鱼！

本记录长期更新，最后更新于 2024年7月2日。



## 桌面环境

### 微软拼音输入法：快捷输入标准 DateTime 字符串

设置路径：`时间和语言 > 语言和区域 > 微软拼音输入法 > 用户自定义短语`

添加新条目：`["dt", "%yyyy%-%MM%-%dd%T%HH%:%mm%:%ss%"]`

### Win11：使用旧版右键菜单

更改注册表并重启资源管理器：

```bat
reg add "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32" /f /ve
tskill explorer
explorer
```

碎碎念：windows 终端有一点好就是在终端启动程序都是 `fork()` 而非 `exec()` 。

### ContextMenuManager：整理右键菜单



ContextMenuManager：[一个纯粹的Windows右键菜单管理程序](https://github.com/BluePointLilac/ContextMenuManager)

## Edge 优化

### 自定义 new tab

致敬流氓巨硬，主页强行 Bing。

幸赖 Chromium 内核，[Custom New Tab](https://chromewebstore.google.com/detail/custom-new-tab/lfjnnkckddkopjfgmbcpdiolnmfobflj) 启动。

## 常用软件

### 文件类

7zip, Everything, SpaceSniffer

### （泛）编程类

[winget](https://winget.run/), git, vscode, windows-terminal

#### winget 启用国内源

替换 USTC 镜像：

```powershell
winget source remove winget
winget source add winget https://mirrors.ustc.edu.cn/winget-source
```

#### git 注册邮箱用户

```bash
git config --global user.name "username"
git config --global user.email "email"
```
