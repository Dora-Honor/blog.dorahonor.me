---
title: 如何突破「启动转换助理」的 4 GB WIM 限制
date: 2026-02-28 13:08:45
tags:
  - Mac
  - Windows
  - Boot Camp
  - 启动转换助理
  - Intel Mac
  - 技术
categories:
  - 经验总结
---

> [!caution]
> - 本教程仅限 Intel Mac。Apple Silicon 平台不适用！
> - 对于超过 4 GB 的 WIM，以我打好最新补丁的 Windows 10 IoT LTSC 2021 为例。

## 前言

在给 Intel Mac 安装 Windows 的过程中，难免会遇到一些麻烦。例如，单个 WIM 大小不能超过 4 GB；若超过，「启动转换助理」则会报错。

考虑到新版本 WIM 普遍大于 4 GB，那有什么办法能突破这个限制呢？以下就是我总结的方法。

## 所需工具

- 一台 Intel Mac 和 Win PC
- 一个容量至少 16 GB，速率至少 5 Gbps，USB 3.2 Gen 1 的空闲 U 盘
- 包含 4 GB 以内 WIM 的 ISO 镜像，需原版启动形式
- 需安装的包含累计大于 4 GB SWM 拆分镜像的 ISO，同样需要原版启动形式
- [UltraISO](https://www.423down.com/1397.html)
- [Dism++](https://github.com/Chuyu-Team/Dism-Multi-language/releases/tag/v10.1.1002.2)
- 一定的**计算机基础**
- **灵活**的头脑

## 准备工作

### 下载原版 Windows 10 LTSC 2019 (x64) ISO 镜像[^1]

- [下载地址 1](https://files.rg-adguard.net/language/36acf39e-bd9f-6f6d-dc1a-a310a649dbaa)（选择所需语言，找到带有 `enterprise_ltsc_2019` 字段的 ISO 镜像）
- [下载地址 2](https://massgrave.dev/windows_ltsc_links)（选择【Windows 10 LTSC 2019】，找到所需语言）

[^1]: 或者其他版本，WIM 镜像体积小于 4 GB 即可

### 准备好打好补丁的 Windows 10 IoT LTSC 2021 (x64) ISO 镜像

#### 下载 LTSC 2021，以备转换 IoT LTSC 2021

- [下载地址 1](https://files.rg-adguard.net/language/397f2844-d1d7-d7de-4b39-906ef9dde1a0)（选择所需语言，找到带有 `enterprise_ltsc_2021` 字段的 ISO 镜像）
- [下载地址 2](https://massgrave.dev/windows_ltsc_links)（选择【Windows 10 LTSC 2021】，找到所需语言）

#### 安装最新补丁

> [!caution]
> 需要在 Win PC 进行操作。

1. 在 [GitHub Releases 页面](https://github.com/adavak/Win_ISO_Patching_Scripts/releases) 下载最新版本工具。
2. 将下载好的工具压缩包解压到合适的位置，复制 LTSC 2021 ISO 到解压的目录。
3. 进入目录，修改 `WIN10UI.ini` 配置文件，将 `wim2esd` 字段值改为 `0`，不转换成 ESD。 
4. 保存配置文件更改，以管理员身份运行 `Start.cmd`。
5. 等待一段时间，同文件夹内会生成 `19044` 开头的最新补丁 ISO 镜像。

#### 转换版本

1. 打开 [Dism++](https://github.com/Chuyu-Team/Dism-Multi-language/releases/tag/v10.1.1002.2)，选择【文件】—【挂载】。
2. 从 `Win_ISO_Patching_Scripts` 开头的工具文件夹中找到 `ISO\sources\install.wim` 并选择。
3. 选择合适的挂载目录，单击【确定】开始挂载以便转换。
4. 以管理员身份运行「命令提示符」，在搜索栏搜索 `cmd`，然后在【命令提示符】处选择【以管理员身份运行】。
5. 参考 [这篇文章](/posts/1148508445/) 进行转换。
6. 别忘了在 [Dism++](https://github.com/Chuyu-Team/Dism-Multi-language/releases/tag/v10.1.1002.2) 保存并卸载 WIM！

### 【可选但推荐】将 WIM 转换成单文件小于 4 GB 的多个 SWM 拆分镜像

1. 打开 [Dism++](https://github.com/Chuyu-Team/Dism-Multi-language/releases/tag/v10.1.1002.2)，选择【文件】—【WIM<--->ESD/SWM】。
2. 从 `Win_ISO_Patching_Scripts` 开头的工具文件夹中找到 `ISO\sources\install.wim` 并选择。
3. 在下面目标路径选择 SWM 镜像目标路径，推荐同目录。
4. 确定后，会弹出「文件拆分」对话框，分卷大小输入 `3686`（只要小于 4 GB 即可），确定。
5. 等待一段时间，会在目标文件夹生成多个例如 `install.swm` 和 `install2.swm` 的 SWM 拆分镜像。注意这些**一个都不能少**！

### 使用所需镜像制作启动盘

> [!caution]
> 该操作会清除 U 盘中所有数据，请确保使用的是不常用的 U 盘，且**没有**重要数据！

1. 打开 [UltraISO](https://www.423down.com/1397.html)。
2. 找到最新补丁 LTSC 2021 ISO 的位置，并打开。
3. 在 ISO 的 `sources` 文件夹删掉原 `install.wim`，将 `install.swm` 和 `install2.swm` 等拆分镜像放入 ISO 并保存。
4. 选择【启动】—【写入硬盘映像】。
5. 在【硬盘驱动器】选择所需 U 盘，写入方式保持默认的 `USB-HDD+` 即可。
6. 单击【写入】开始制作启动盘。等待一段时间。

## 开始安装

在 Mac 底部程序坞选择【启动台】—【其他】—【启动转换助理】，或者按 `Cmd-Space` 全局搜索「启动转换助理」并启动。

> [!tip]
> 如果使用的是 Windows 键盘，则是按 `Win-Space` 全局搜索「启动转换助理」并启动。

### 使用「启动转换助理」创建分区、下载支持软件和安装镜像

跟随指引一路下一步，找到 LTSC 2019 ISO 所在位置（必须是 Mac 本地磁盘）并选择，按需求调整 Windows 分区大小。

开始安装，等待一段时间完成后会自动重启到 Windows 安装界面。

在 Windows 安装界面一路下一步，自动安装。

重启后在设置界面按照自己喜好进行设置，即可进入桌面。

### 提取并复制所需文件

连接做好的启动盘，将 D 盘中的 `$WinPEDriver$`、`BootCamp` 文件夹和 `AutoUnattend.xml` 复制到启动盘。

### 从启动盘启动进行安装

确保启动盘已连接。重启 Mac 按住 `Opt` 键进入启动菜单，选择启动盘选项。

> [!tip]
> 如果使用的是 Windows 键盘，则是按住 `Alt` 键进入启动菜单。

同样，在 Windows 安装界面一路下一步进行自动安装。安装完成后会重启。

### 安装驱动支持软件

确保启动盘已连接。打开【此电脑】，在启动盘中找到 `BootCamp\Setup.exe` 并**以管理员身份运行**。

一路下一步进行安装。

### 启动 Apple Software Update 检查驱动更新

打开「开始」菜单中找到【Apple Software Update】，检查更新。

如果有，进行更新。

## 【可选】清理以前的 Windows 安装文件

打开「开始」菜单，找到【Windows 管理工具】—【磁盘清理】。

选择并扫描 C 盘，然后单击【清理系统文件】。

勾选【以前的 Windows 安装文件】，单击【确定】，开始清理。
