# Lenovo-ideapad-110-15IKB-Hackintosh

# 中文版｜[English]( README-EN.md)

## 电脑配置

|   规格   |                           详细信息                           |
| :------: | :----------------------------------------------------------: |
| 电脑型号 |                     联想Ideapad110-15IKB                     |
| 支持系统 | macOS Catalina 10.15.x / macOS Mojave (理论支持，更新到10.15后未做测试)+Windows 10（使用Boot Camp）/ macOS Big Sur 11 |
|  处理器  |                    英特尔 酷睿 i5 - 7200U                    |
|   内存   |              原厂自带一条4G，后自己另外加一条4G              |
|   硬盘   |              原装辣鸡机械硬盘，自己更换为860EVO              |
|   显卡   |                    Intel HD Graphics 620                     |
|  显示器  |                     15.6英寸 TN 1366*768                     |
|   声卡   |              Conexant CX20751/2  AppleALC ID=21              |
|   网卡   |                      更换为BCM94360CS2                       |

## 引导概况

- 关于EFI，现有`Clover`和`OpenCore`两个引导。
  
  - `Clover`  **仅发布在我替换到OC之后的最后一版**，有兴趣可以尝试自己更新`CLOVERX64.efi`、`Kext`以及`driver`。
  
- `OpenCore`  以后主要维护的引导（主要是实在没有精力去在Clover和OC之间来回切换做兼容性测试）。OC目前版本0.6.0，基于[Acidanthera](https://github.com/acidanthera)官方[Release](https://github.com/acidanthera/OpenCorePkg/releases)，理论上在每月初官方版本OC新发布后，会在一周内跟进更新。
  
    ###### 注：`（新版OC 0.6.0已经支持安装macOS Big Sur，但由于尝试安装BETA版系统所造成的数据丢失或其他一切损失,本人不负任何责任）`
  
- ### 安装前准备
  
  - 开机按`F2`进入`BIOS`
  - 设置 `Secure Boot` 为 `Disabled`;
  - 设置`FastBoot`为`Disable`
  - 建议远景论坛寻找教程以禁用CFG Lock
  - `F10` 保存设置并重启

- ### 安装后操作
  
  - 安装好系统，进入系统
  - 找到`终端`执行一下：`sudo spctl --master-disable`

- ### OC 与 Clover之间切换：
  
  - 例如Clover 转 OC
  
  - 先设置OC启动
  
  - 第一次重启，选择`reset nvram`，这时之前的启动设置会清除了
  
  - 再次设置对应的`EFI`启动即可

- 镜像下载
  
  - [[**黑果小兵的部落阁**] :【黑果小兵】原版镜像](https://blog.daliansky.net/categories/下载/镜像/)
- 使用[**gibMacOS**](https://github.com/corpnewt/gibMacOS)
  
- EFI下载
  
  - [Releases](https://github.com/WenvyG/Lenovo-ideapad-110-15IKB-Hackintosh/releases)

- 更新日志  
  
  - [Changelog](Changelog.md)

## 正常工作

- Intel核心显卡
- Wi-Fi与蓝牙（已将原装的高通网卡替换为`BCM94360CS2`）
- 显示器亮度调节
- 触摸板 
- USB定制
- 声卡
- 本机自带摄像头
- 有线网卡
- `OpenCore`下`NVRAM`正常，可以使用`Boot Camp`在macOS和Windows10之间自由切换

## 不正常工作

- 自带AMD Radeon 530独立显卡（建议在BIOS在将显卡设置为只运行核显，否则在macOS下温度较高。也可以选择采用[SSDT-Disable-DGPU](SSDT-Disable-DGPU.aml)屏蔽独显，不过这个方法并没有在OC中测试）
- 其他硬件以及对安装到使用过程有问题的可以在[Issues](https://github.com/WenvyG/Lenovo-ideapad-110-15IKB-Hackintosh/issues)中回馈给我。

## 鸣谢

- 感谢[Apple](https://www.apple.com/cn/)的macOS
- 感谢 [Acidanthera](https://github.com/acidanthera) 提供 [AppleALC](https://github.com/acidanthera/AppleALC)，[Lilu](https://github.com/acidanthera/Lilu)，[OpenCorePkg](https://github.com/acidanthera/OpenCorePkg)，[VirtualSMC](https://github.com/acidanthera/VirtualSMC)，和 [WhateverGreen](https://github.com/acidanthera/WhateverGreen)。
- 感谢 [apianti](https://sourceforge.net/u/apianti)，[blackosx](https://sourceforge.net/u/blackosx)，[blusseau](https://sourceforge.net/u/blusseau)，[dmazar](https://sourceforge.net/u/dmazar) 和 [slice2009](https://sourceforge.net/u/slice2009) 提供 [Clover](https://github.com/CloverHackyColor/CloverBootloader)。
- 感谢 [daliansky](https://github.com/daliansky) 提供[macOS Catalina镜像下载](https://blog.daliansky.net/categories/下载/镜像/)。
- 感谢[corpnewt](https://github.com/corpnewt)提供[gibMacOS](https://github.com/corpnewt/gibMacOS)
- 感谢[corpnewt](https://github.com/corpnewt)提供[ProperTree](https://github.com/corpnewt/ProperTree)

