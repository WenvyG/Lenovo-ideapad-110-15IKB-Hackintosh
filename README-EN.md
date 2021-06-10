# Lenovo-ideapad-110-15IKB-Hackintosh

# [中文版](README.md)｜English

## Detail of my computer

| Specifications |                  Detail                  |
| :------------: | :--------------------------------------: |
|     Model      |         Lenovo Ideapad110-15IKB          |
|     System     | Windows10 (Boot Camp) / macOS Big Sur 11 |
|      CPU       |          Intel Core i5 - 7200U           |
|     Memory     |             8GB DDR4 2133MHz             |
|      SSD       |              Samsung 860EVO              |
|    Graphics    |          Intel HD Graphics 620           |
|    Monitor     |           15.6inch TN 1366*768           |
|     Audio      |    Conexant CX20751/2  AppleALC ID=21    |
| Wireless Card  |               BCM94360CS2                |

## Situation of EFI

#### Here are two different versions of the EFIs,  `Clover`and`OpenCore`.

- **`Clover`**   It will NO LONGER be maintained,  so I will only release the lastest version before I switch to Opencore,  but you still can try to upgrade the `CLOVERX64.efi`,  `Kexts`and`drivers`by yourself.

- **`OpenCore`**  This one will be maintained by me for a long time. OpenCore' s version is 0.6.1, It's base on the [Acidanthera](https://github.com/acidanthera)'s offical [Release](https://github.com/acidanthera/OpenCorePkg/releases), theoretically I will update the latest version of OC in a week after it is released.

  ##### PS. 

  * **`OC 0.7.0 now is support to install macOS Big Sur to your disk, it's a good news for Hackintosh. Enjoy it!`**
  * **I prefer to use [`ProperTree`](https://github.com/corpnewt/ProperTree) when you are editing config.plist.**

- ### BIOS Settings
  
  #### Disable
  
  - `Secure Boot` 
  - `FastBoot`
  - `CFG Lock` (recommended)

- ### EFI
  
  - [Releases](https://github.com/WenvyG/Lenovo-ideapad-110-15IKB-Hackintosh/releases)

  ### Changelog
  
  - [Changelog](Changelog.md)

## What works:

- Intel HD Graphins 620
- Wi-Fi and Bluetooth（using `BCM94360CS2`）
- Monitor and 
- Trackpad 
- USB
- Audio
- Camera
- Realtek RTL8106E
- NVRAM (when using OC)

## What not woks

- AMD Radeon 530 ( It is recommended to disable by bios setting or using [SSDT-Disable-DGPU](SSDT-Disable-DGPU.aml)（I‘m not sure the SSDT's Compatibility in OpenCore) , because it will make your computer run at a very high temperature. )
- Any other issues you may have can be feed back to me in [Issues](https://github.com/WenvyG/Lenovo-ideapad-110-15IKB-Hackintosh/issues).

## Credits

- Thanks to [Apple](https://www.apple.com/cn/) for providing macOS
- Thanks to [Acidanthera](https://github.com/acidanthera)  for providing  [AppleALC](https://github.com/acidanthera/AppleALC), [Lilu](https://github.com/acidanthera/Lilu), [OpenCorePkg](https://github.com/acidanthera/OpenCorePkg), [VirtualSMC](https://github.com/acidanthera/VirtualSMC) and [WhateverGreen](https://github.com/acidanthera/WhateverGreen).
- Thanks to [apianti](https://sourceforge.net/u/apianti), [blackosx](https://sourceforge.net/u/blackosx), [blusseau](https://sourceforge.net/u/blusseau), [dmazar](https://sourceforge.net/u/dmazar) and [slice2009](https://sourceforge.net/u/slice2009)  for providing  [Clover](https://github.com/CloverHackyColor/CloverBootloader).
- Thanks to [corpnewt](https://github.com/corpnewt) providing [gibMacOS](https://github.com/corpnewt/gibMacOS) and [ProperTree](https://github.com/corpnewt/ProperTree).

