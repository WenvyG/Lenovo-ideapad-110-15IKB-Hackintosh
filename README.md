# Lenovo-ideapad-110-15IKB-Hackintosh


## 电脑配置

|   规格   |                           详细信息                           |
| :------: | :----------------------------------------------------------: |
| 电脑型号 |                     联想Ideapad110-15IKB                     |
| 支持系统 | macOS Catalina 10.15.x / macOS Mojave (理论支持，更新到10.15后未做测试) |
|  处理器  |                    英特尔 酷睿 i5 - 7200U                    |
|   内存   |                  原厂自带一条4G，后自己另外加一条4G               |
|   硬盘   |              原装辣鸡机械硬盘，自己更换为860EVO              |
|   显卡   |                    Intel HD Graphics 620                     |
|  显示器  |                     15.6英寸 TN 1366*768                     |
|   声卡   |              Conexant CX20751/2  AppleALC ID=21              |
|   网卡   |                      更换为BCM94360CS2                       |

## 引导概况
- 关于EFI，现有`Clover`和`OpenCore`两个引导。

  - `Clover`  仅发布在我替换到OC之后的最后一版，有兴趣可以尝试自己更新`CLOVERX64.efi`、`Kext`以及`driver`。
  - `OpenCore`  以后主要维护的引导（主要是实在没有精力去在Clover和OC之间来回切换做兼容性测试）。OC目前版本0.5.9，基于[Acidanthera](https://github.com/acidanthera)官方[Release](https://github.com/acidanthera/OpenCorePkg/releases)，每月初新发布后，应该会在一周内跟进更新。

- ### 安装前准备

  - 开机按`F2`进入`BIOS`
  - 设置 `Secure Boot` 为 `Disabled`;
  - 设置`FastBoot`为`Disable`
  - （建议将设置显卡为只运行核显，否则在macOS下温度较高，也可以选择采用SSDT屏蔽独显）
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

- EFI下载

  - [Releases](123)

- 更新日志  

  - [Changelog](Changelog.md)

## 正常工作

- Intel核心显卡
- 电源
- Wi-Fi与蓝牙（已将原装的高通网卡替换为`BCM94360CS2`）
- 显示器亮度调节
- 触摸板 
- USB定制
- 声卡
- 本机自带摄像头
- 有线网卡

## 不正常工作

- 自带AMD Radeon 530独立显卡
- 其他硬件以及对安装到使用过程有问题的可以在[Issues](123)中回馈给我

## 鸣谢

- 感谢[Apple](https://www.apple.com/cn/)的macOS
- 感谢 [Acidanthera](https://github.com/acidanthera) 提供 [AppleALC](https://github.com/acidanthera/AppleALC)，[Lilu](https://github.com/acidanthera/Lilu)，[OpenCorePkg](https://github.com/acidanthera/OpenCorePkg)，[VirtualSMC](https://github.com/acidanthera/VirtualSMC)，和 [WhateverGreen](https://github.com/acidanthera/WhateverGreen)。
- 感谢 [apianti](https://sourceforge.net/u/apianti)，[blackosx](https://sourceforge.net/u/blackosx)，[blusseau](https://sourceforge.net/u/blusseau)，[dmazar](https://sourceforge.net/u/dmazar) 和 [slice2009](https://sourceforge.net/u/slice2009) 提供 [Clover](https://github.com/CloverHackyColor/CloverBootloader)。
- 感谢 [daliansky](https://github.com/daliansky) 提供[ macOS Catalina](https://blog.daliansky.net/categories/下载/镜像/)镜像下载链接

