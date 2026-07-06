---
title: mskk Windows 7 SP1 简体中文最终版
date: 2026-06-15 22:30:53
tags:
  - Windows
  - Windows 7
  - 镜像
  - 封装
categories: Windows
draft: true
---

## 系统截图

![](https://img.dorahonor.me/2026/06/16/001854_01.webp)

![](https://img.dorahonor.me/2026/06/16/001854_02.webp)

![](https://img.dorahonor.me/2026/06/16/001854_03.webp)

![](https://img.dorahonor.me/2026/06/16/001854_04.webp)

![](https://img.dorahonor.me/2026/06/16/001854_05.webp)

![](https://img.dorahonor.me/2026/06/16/001854_06.webp)

![](https://img.dorahonor.me/2026/06/16/001854_07.webp)

![](https://img.dorahonor.me/2026/06/16/001854_08.webp)

![](https://img.dorahonor.me/2026/06/16/003511_09.webp)

![](https://img.dorahonor.me/2026/06/16/003511_10.webp)

![](https://img.dorahonor.me/2026/06/16/003511_11.webp)

## 更新说明

- 使用 [UpdatePack7R2](https://blog.simplix.info/update7/) 安装更新至最新
- 集成 BypassESU
- 集成 DirectX、.NET Framework 4.8、VCRedist、Adobe Flash Player 34
- 集成 Internet Explorer 11

## 系统特色

- 以微软原版 Windows 7 SP1 镜像为标准，集成更新并做少许优化
- 无 OEM 信息，不锁主页，主页默认为 `about:Tabs` 新标签页
- 支持 Windows Update 在线更新
- 集成公文标准字体 **仿宋_GB2312**、**楷体_GB2312**、**方正小标宋简**
- 集成 Windows 8 版 Microsoft YaHei UI (`msyh.ttc`) 和 Microsoft Jhenghei UI (`msjh.ttc`) 字体
- 自带两款精美主题
- 断网封装保障安全
- 无人值守安装，启用 Administrator 管理员账户，跳过 OOBE
- 使用 IT 天空最新万能驱动 7 驱动包，支持更多硬件
- 使用 IT 天空 Easy Sysprep v4 最新版封装

## 安装软件

- 7-Zip 19.00
- Adobe Flash Player 34
- Bandizip 6.29
- Honeyview 5.49
- K-Lite Codec Pack 19.7.5 Mega
- Microsoft Edge 88
  - 注意企业版桌面没有快捷方式
- Notepad3
- PotPlayer 64-bit 1.7.18958
  - PotPlayer 1.7.18958
- QuickTime 7.7.9
- VLC media player 3.0.23
- WinRAR 5.50
- 教育考试专用版 WPS Office 11.1.0.10009
- 谷歌拼音输入法 2.7
- 极点五笔十周年纪念版
- 千千静听 7.0.4

## 优化设置

### 任务栏

- 关闭操作中心
- 始终合并

### 安全相关

- 关闭 UAC、Smartscreen 筛选器、安全警告、Windows Defender

### 「开始」菜单

- 关闭突出显示新安装的程序

### 文件资源管理器

- 显示所有文件扩展名、隐藏文件（不含受保护的操作系统文件）
- 隐藏可执行文件盾牌、NTFS 蓝色双箭头压缩标识
- 显示菜单栏
- 禁止自动播放
- 在单独的进程中打开文件夹窗口
- 资源管理器标题栏显示完整路径
- 将语言栏隐藏到任务栏，隐藏帮助按钮

### 桌面图标

- 用户文件夹
- 计算机
- 网络
- 回收站
- Internet Explorer

### Internet Explorer

- 当创建新选项卡时，始终切换到新选项卡
- 其他程序从当前窗口的新选项卡打开链接
- 启动表单的自动完成功能
- 关闭建议的网站
- 跳过 IE 首次运行设置
- 将同时可用下载数目调整到 10
- 关闭自动更新

### Windows Update

- 自动安装无需重启的更新
- 更新挂起时，如果有用户登录，不自动重启计算机
- Windows 更新不包括驱动程序
- Windows 更新不包括恶意软件删除工具
- 将 Windows Update 自动更新调整为 **仅检查更新**

### 记事本

- 启用自动换行
- 始终显示状态栏

### 网络

- 关闭防火墙

### 服务优化

- 禁用错误报告
- 禁用客户体验改善计划
- 禁用 NTFS 链接跟踪服务

### WinRAR

- 锁定 WinRAR 工具栏

### Windows Media Player

- 不显示首次使用对话框

### 其他

- 禁用蓝屏时自动重启
- 关闭休眠
- 禁用组件堆栈、更新解压模块、系统日志
- 禁用组件堆栈文件备份
- 崩溃时写入调试信息为 **小内存转储 (256K)**
- 禁用账号登录日志报告
- 禁用 WfpDiag.ETL 日志

## 精简组件

### 非旗舰版

- DVD Maker
- Media Center (媒体中心)
- 入门
- .NET assembly 缓存
- 安全中心
- Windows Anytime Upgrade
- Windows Defender - Microsoft Defender 防病毒
- Manifest 备份
- 边栏
  - 小工具
- 服务结束通知 (EOSNotify)
- Windows 客户体验改善计划 CEIP (SQM)

### 旗舰版

除 **DVD Maker**、**Media Center (媒体中心)**、**Windows Anytime Upgrade**、**入门**、**边栏**、**小工具** 外上述所有组件。

- .NET assembly 缓存
- 安全中心
- Windows Defender - Microsoft Defender 防病毒
- Manifest 备份
- 服务结束通知 (EOSNotify)
- Windows 客户体验改善计划 CEIP (SQM)

## 安装方法

以下是举例常用安装工具的方法。其他方法不再阐述。

### [Dism++](https://github.com/Chuyu-Team/Dism-Multi-language)

1. 在主界面选择 `文件` - `释放镜像`，或者按 `Ctrl-N` 进入「释放映像」窗口
2. 找到镜像所在位置并选择
3. 选择所需安装版本
4. 选择安装目录（一般为 C 盘）
5. 勾选 `添加引导`（如果需要）和 `格式化`
6. 单击 `确定` 开始安装

### WinNTSetup

1. 找到镜像所在位置并选择
2. 选择引导分区
3. 选择安装目录（一般为 C 盘）
4. 选择安装版本
5. 开始安装

## 注意事项

请务必使用 **纯净 PE** 和 **安装工具** 安装！如果安装后出现桌面图标和截图不一致，被安装流氓软件，主页被篡改且无法还原等现象，皆为使用安装导致！

下载后请核对文件信息是否一致，如果不一致请勿使用！

如果使用 U 盘安装，安装结束进系统前务必拔掉 U 盘，否则会造成盘符错乱！

## 免责声明

本系统仅限个人学习和演示部署技术，作者不承担任何技术及版权问题；严禁用于商业用途或非法传播，否则自负法律责任。请在下载后 24 小时内删除，如果您觉得满意，请购买正版。

## 下载地址

待上传

### 64 位

旗舰版、VL 专业版、企业版

![](https://img.dorahonor.me/2026/06/16/000552_20260616000552368.webp)

``` hash
文件: D:\ISO\mskk_win7_sp1_peu_x64_final.esd
大小: 9053348726 字节
修改时间: 2026年6月15日, 22:42:32
MD5: CD6B9ED7569E4035528BACD421A74696
SHA1: 72ED4D3F18E981C46CE9474B7E31F9D9447AE5F6
CRC32: 0CE9F864
```

家庭普通版、家庭高级版

### 32 位

旗舰版、VL 专业版、企业版

简易版、家庭普通版、家庭高级版

## 致谢
