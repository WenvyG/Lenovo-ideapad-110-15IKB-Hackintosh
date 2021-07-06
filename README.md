# Lenovo-ideapad-110-15IKB-Hackintosh

中文版｜[English]( README-EN.md)

## 电脑配置

|   规格   |                 详细信息                  |
| :------: | :---------------------------------------: |
| 电脑型号 |           联想 Ideapad110-15IKB            |
| 支持系统 | Windows 10（Boot Camp）/ macOS Big Sur 11 / macOS Monterey Beta |
|  处理器  |          英特尔 酷睿 i5 - 7200U           |
|   内存   |    原厂自带一条 4G，后自己另外加一条 4G     |
|   硬盘   |                三星 860EVO                |
|   显卡   |           Intel HD Graphics 620           |
|  显示器  |           15.6 英寸 TN 1366*768            |
|   声卡   |    Conexant CX20751/2  AppleALC ID=21     |
|   网卡   |             更换为 BCM94360CS2             |

## 引导

### 关于 EFI，现有`Clover`和`OpenCore`两个引导：

- `Clover`  **仅发布在我替换到 OC 之后的最后一版**，有兴趣可以尝试自己更新，发现更多可能性。

- `OpenCore`  以后主要维护的引导（主要是实在没有精力去在 Clover 和 OC 之间来回切换做兼容性测试）。OC 目前版本 0.7.1，基于 [Acidanthera](https://github.com/acidanthera) 官方 [Release](https://github.com/acidanthera/OpenCorePkg/releases)。理论上在每月初官方版本 OC 新发布后，会在一周内跟进更新。
  - 最新版 `OC 0.7.1` 支持安装最新版的 `macOS Monterey Beta`，但由于尝试安装Beta版软件所造成的数据等损失本人概不负责。
  - **编辑 config.plist 时推荐使用 [`ProperTree`](https://github.com/corpnewt/ProperTree)。** Xcode 在编辑 DATA 类型时会有问题；OpenCore Configurator 更新不及时且不时会有 BUG，可能会损换文件结构；不推荐使用。

#### OC 与 Clover 之间切换：

##### Clover 转 OC：

1. 先设置 OC 启动
2. 第一次重启，选择`reset nvram`，这时之前的启动设置会清除了
3. 再次设置对应的`EFI`启动即可

##### Clover 转 OC：

1. 从 OC 启动
2. 选择`reset nvram`
3. 选择 macOS 所在磁盘启动

## 安装

### 安装前准备

- 开机按`F2`进入`BIOS`
- 设置 `Secure Boot` 为 `Disabled`;
- 设置`FastBoot`为`Disable`
- 建议远景论坛寻找教程以禁用 CFG Lock
- `F10` 保存设置并重启

### 安装后操作

- 安装好系统，进入系统

- 找到`终端`执行如下代码，以允许安装/打开第三方应用：

```sh
  sudo spctl --master-disable
```

## 镜像及 EFI

### 镜像下载

  - [**黑果小兵的部落阁**] :[【黑果小兵】原版镜像](https://blog.daliansky.net/categories/下载/镜像/)
  - 使用 [**gibMacOS**](https://github.com/corpnewt/gibMacOS)

### EFI 下载

- [Releases](https://github.com/WenvyG/Lenovo-ideapad-110-15IKB-Hackintosh/releases)
### 更新日志  

- [Changelog](Changelog.md)
## 使用情况
### 正常工作

- Intel 核心显卡
- Wi-Fi 与蓝牙（已将原装的高通网卡替换为`BCM94360CS2`）
- 显示器亮度调节
- 触摸板 
- USB 定制
- 声卡
- 本机自带摄像头
- 有线网卡
- `OpenCore`下`NVRAM`正常，可以使用`Boot Camp`在 macOS 和 Windows10 之间自由切换

### 不正常/不工作

- 自带 AMD Radeon 530 独立显卡（建议在 BIOS 在将显卡设置为只运行核显，否则在 macOS 下温度较高。也可以选择采用 [SSDT-Disable-DGPU](SSDT-Disable-DGPU.aml) 屏蔽独显，不过这个方法并没有在 OC 中测试）
- 其他硬件以及对安装到使用过程有问题的可以在 [Issues](https://github.com/WenvyG/Lenovo-ideapad-110-15IKB-Hackintosh/issues) 中回馈给我。

## 鸣谢

- 感谢 [Apple](https://www.apple.com/cn/) 的 macOS
- 感谢 [Acidanthera](https://github.com/acidanthera) 提供 [AppleALC](https://github.com/acidanthera/AppleALC)，[Lilu](https://github.com/acidanthera/Lilu)，[OpenCorePkg](https://github.com/acidanthera/OpenCorePkg)，[VirtualSMC](https://github.com/acidanthera/VirtualSMC)，和 [WhateverGreen](https://github.com/acidanthera/WhateverGreen)。
- 感谢 [apianti](https://sourceforge.net/u/apianti)，[blackosx](https://sourceforge.net/u/blackosx)，[blusseau](https://sourceforge.net/u/blusseau)，[dmazar](https://sourceforge.net/u/dmazar) 和 [slice2009](https://sourceforge.net/u/slice2009) 提供 [Clover](https://github.com/CloverHackyColor/CloverBootloader)。
- 感谢 [daliansky](https://github.com/daliansky) 提供 [macOS Catalina 镜像下载](https://blog.daliansky.net/categories/下载/镜像/)。
- 感谢 [corpnewt](https://github.com/corpnewt) 提供 [gibMacOS](https://github.com/corpnewt/gibMacOS) 和 [ProperTree](https://github.com/corpnewt/ProperTree)

## 注：

- **我所分享的 EFI 引导文件的目标人群是拥有一定黑苹果基础的的同机型用户，需要自己修改`config.plist`的中的三码。**

- **关于关闭`CFGLock`，可在远景论坛自行搜索` "联想"、”解锁 CFG“`。**

  