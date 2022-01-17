# 微星 B360M 迫击炮 (钛金版) 黑苹果 OpenCore EFI

## EFI 介绍

<img src="Images/Readme/Image.jpg" align="right" width="360" />

此 EFI 使用`iMac19,1`机型，微星 B360M 迫击炮 (钛金版) 的绝大部分用户可通过修改使用，核显 + 独显共同硬解，默认启用全部 USB 端口，[OpenCore](https://github.com/acidanthera/OpenCorePkg) 版本：0.7.7

> 注意：此 EFI 只是个人的构建分享，并标注了简单的使用提示，不是标准的 OpenCore 黑苹果安装指南，如果你需要标准安装指南请跳转至 [Dortania's Getting Started](https://dortania.github.io/getting-started/) 查看。在首次安装或更新硬件后启动黑苹果可能会遇到一些问题，虽然大部分问题都可以解决，但事实上确实存在部分没办法解决的问题，甚至可以说有一定的运气成分在里面，如果你要应用此 EFI 建议使用接近我的配置，才能尽可能地拥有相同的使用体验。

#### 关于本机
![](https://raw.githubusercontent.com/GeQ1an/MSI-B360M-MORTAR-HACKINTOSH-OPENCORE-EFI/master/Images/Screenshots/About.png)

### 可正常工作
- [x] 声卡（板载）/ 网卡（板载）
- [x] 显卡（核显 + 独显）/ 硬解 4K（HEVC + H.264）
- [x] WiFi（PCI-E 设备） / 蓝牙（PEI-E 载 USB 设备）
- [x] 隔空投送 / 接力 / 随航
- [x] FaceTime / iMessage
- [x] Apple Music / Apple TV Plus
- [x] 睿频 / HWP 变频 / 原生电源管理
- [x] 睡眠 / 键盘、鼠标唤醒
- [x] 其他白果功能（99%）

### 我的配置

|                 硬件 | 型号                                                  | 
|--------------------:|:------------------------------------------------------|
|                 主板 | 微星 B360M 迫击炮                                      |
|               处理器 | 英特尔酷睿 i5-9600K                                     |
|                 显卡 | 公版 RX 570 4GB (VBIOS 品牌为微星)                      |
|                 硬盘 | 西部数据 SN750 500GB                                   |
|                 内存 | 光威悍将 8GB DDR4 2666MHz x 2                          |
|           无线 + 蓝牙 | 奋威 FV-T919 无线网卡 (BCM94360CD 双频 1750M + 蓝牙 4.0) |
|    机箱 + 电源 + 散热 | 乔思伯 U3 + 台达 NX450 + 利民 AS120 + ARCTIC F12 PWM     |
|               显示器 | 飞利浦 276E8VJSB（27 英寸 4K 分辨率）                     |
|       摄像头 + 麦克风 | LOGITUBO 928 自动对焦带双降噪麦克风摄像头                   |
|                 音箱 | 漫步者 R201T 北美版 2.1 桌面音箱                          |
|                 键盘 | iQunix F96 珊瑚海（有线茶轴 RGB 版）                      |
|                 鼠标 | 罗技 MX Master 3 (使用优联连接，以方便在 BIOS 中使用)       |

### 兼容的配置

|                 硬件 | 型号                                                                                                     | 
|--------------------:|:--------------------------------------------------------------------------------------------------------|
|                 主板 | 微星 B360M 迫击炮 (钛金版)                                                                                 |
|               处理器 | 英特尔第 8 代、第 9 代酷睿处理器 (推荐拥有核显的版本)                                                            |
|                 显卡 | RX 400 系列 / RX 500 系列 (560 以上) / RX VEGA 系列 / Radeon VII / RX 5000 系列 / RX 6000 系列 (除 6700 XT)  |
|                 硬盘 | 除了几个特例 (如三星 PM981 / PM991)，基本都可以                                                               |
|                 内存 | 除了非常差的，基本都可以                                                                                     |
|           无线 + 蓝牙 | 黑苹果免驱版无线 + 蓝牙 PCI-E 网卡都可以                                                                      |
|       摄像头 + 麦克风 | macOS 免驱版都可以                                                                                         |
|    机箱 + 电源 + 风扇 | 根据个人喜好和 CPU、显卡的功率来决定                                                                           |
|               显示器 | 根据个人喜好选择 (推荐 4K 及以上分辨率)                                                                        |
|    键盘 + 鼠标 + 音箱 | 根据个人喜好选择                                                                                            |
|             其它外设 | 根据个人喜好选配 (注意 macOS 兼容性)                                                                          |

*Tips 1：如果选购 RX 500 系列显卡优先选择蓝宝石品牌，其次选择迪兰恒进、华硕和微星，尽量不选择盈通和讯景，一定避开 RX 580 2048SP 版本！*<br>
*Tips 2：推荐选购 RX 5000 系列和 RX 6000 系列新显卡，蓝宝石在 RX 6000 系列比较缩水，不建议优先选择，一定避开 RX 6700 XT。使用 RX 6800 / RX 6800 XT / RX 6900 XT 显卡要求 macOS 最低系统版本为 Big Sur 11.4 beta 1，使用 RX 6600 / RX 6600 XT 显卡要求 macOS 最低系统版本为 Monterey 12.1 beta 1。*<br>
*Tips 3：选购硬盘建议避开三星，特别是 macOS Monterey 会因为 TRIM 的原因导致开机时间变长（970 EVO 几乎全军覆没，980 PRO 听天由命）。推荐选择西数 SN850 / SN750、英特尔 760P 等比较稳定的硬盘。*<br>

## 更新记录
#### 2022.01.17
* 调整配置文件部分选项

*具体为：关闭 Booter > Quirks > EnableWriteUnprotector & ProtectUefiServices，开启 RebuildAppleMemoryMap & SyncRuntimePermissions (理论上兼容性更好，避免部分机器出现启动问题)；关闭 Misc > Security > BlacklistAppleUpdate (OC 0.7.0 版本开始已作废)；关闭 UEFI > Output > SanitiseClearScreen (BuiltinGraphics 渲染方式下该选项不生效)。此次调整为增强兼容性、关闭不必要的选项，之前的设置不影响使用，如无特殊需求，可等到下次 OC 更新时再更新。*

#### 2022.01.12
* 关闭 ACPI > Patch > 0 用于修改 GPRW 电源管理 S4 级为 S3 级的补丁
* 关闭 Kernel > Add > 10 & 11 用于开启 CPUFriend 的 Kexts

*秉承 “能免则免、能简则简” 的原则，经反复测试，现在不需要再将 GPRW 降级为 S3 即可正常睡眠，于是默认关闭这个补丁，如果更新后睡眠不正常（表现为睡眠即醒）请尝试重新打开这个补丁；默认关闭 CPUFriend，以方便基础用户使用，有需要自行定制后打开即可。*

#### 2022.01.11
* 更新 OpenCore 至 0.7.7 正式版
* 更新 Lilu \ AppleALC \ WhateverGreen Kexts 至官方最新版，移除 USBPower Kext
* 更新 OpenRuntime \ OpenCanopy \ OpenHfsPlus 驱动
* 整理 SSDT 为更主流的搭配，添加 SSDT-EC-USBX，更新 SSDT-PLUG，移除 SSDT-PM 合并至 SSDT-PLUG

*OC 0.7.7 正式版的配置文件新增和调整了一些条目，建议按照使用习惯重新配置。支持 macOS 12.2，正式版发布后可直接升级。*

<details><summary>2021 年更新记录</summary>

#### 2021.12.09
* 更新 OpenCore 至 0.7.6 正式版
* 更新 Lilu \ AppleALC \ VitualSMC Kexts 至官方最新版，更新 USBInjectAll Kext 为更新的修改版
* 更新 OpenRuntime \ OpenCanopy 驱动

*OC 0.7.6 正式版的配置文件新增和调整了一些条目，建议按照使用习惯重新配置。此版本开始默认将自动检测 HiDPI，一般无需手动设置，但可能需要重置一次 NVRAM（如果更新后遇到开机苹果 logo 显示不正常的情况）；同步 OC 官方默认隐藏引导选择界面中的辅助工具，按空格键显示；支持 macOS 12.1，正式版发布后可直接升级。*

#### 2021.11.10
* 更新 OpenCore 至 0.7.5 正式版
* 更新 Lilu \ AppleALC \ WhateverGreen \ VitualSMC Kexts 至官方最新版
* 更新 OpenRuntime \ OpenCanopy \ OpenHfsPlus 驱动
* 修改配置文件 Misc > Security > DmgLoading 参数为`Signed`\ Misc > Security > SecureBootModel 参数为`Default`（详见 [Q&A 条目 9](#9-为什么要开启安全启动和-sip)）；修改配置文件 NVRAM > Add > 7C436110-XXXX > csr-active-config 参数为`00000000`\ Misc > Security > AllowToggleSip 参数为 `True/Yes`（详见 [Q&A 条目 9](#9-为什么要开启安全启动和-sip)）；修改配置文件 Misc > Boot > TakeoffDelay 参数为`5000`（单位：毫秒）以提高兼容性

**注意事项**：1. 如果你仍在使用 **macOS Catalina 10.15 或更早版本**系统，需要**修改 OC 配置文件** UEFI > APFS 下的 **MinData** 和 **MinVersion** 参数为`-1`（详见 [Q&A 条目 10](#10-为什么使用-catalina-需要额外修改配置)）；2. 更新或安装 **macOS Big Sur 11.3.1 及以后版本**，请提前**定制 USB 并启用**（详见 [Q&A 条目 11](#11-为什么一定要定制-usb)）。<br>
<br>
*OC 0.7.5 正式版的配置文件新增和删除了若干条目，此次配置文件改动较大，建议按照使用习惯重新配置。支持 macOS 12.1，正式版发布后可直接升级（因近几个月事务繁多，直到今天才得以更新，向所有用户道一声抱歉）。*

#### ~~2021.07.12~~
* ~~更新 OpenCore 至 0.7.1 正式版~~
* ~~更新 Lilu \ AppleALC \ WhateverGreen \ VitualSMC \ IntelMausi \ CPUFriend Kexts 至官方最新版，添加 NVMeFix Kext 并启用~~
* ~~更新 OpenRuntime \ OpenCanopy 驱动，替换 HfsPlus 驱动为 OpenHfsPlus 驱动，移除 ExFatDxe 驱动~~
* ~~替换 VerifyMsrE2 工具为 ControlMsrE2 工具~~
* ~~更新`/EFI/OC/Resources`启动主题相关文件~~

*~~OC 0.7.1 正式版的配置文件新增和删除了若干条目，建议按照使用习惯重新配置。此版本开始默认启用启动主题，如需关闭可将 OC 配置文件 Misc > Boot > PickerMode 的`External`修改为`Builtin`；支持 macOS 11.5，正式版发布后可直接升级（因近几个月事务繁多，直到今天才得以更新，向所有用户道一声抱歉）。~~ 因网络问题，此更新一直未得以上传。*

#### 2021.02.08
* 更新 OpenCore 至 0.6.6 正式版
* 更新 Lilu \ AppleALC \ WhateverGreen \ VitualSMC Kexts 至官方最新版
* 更新 OpenRuntime \ OpenCanopy 驱动
* 更新`/EFI/OC/Resources`启动主题相关文件
* 移除`/EFI/OC/Bootstrap/Bootstrap.efi`OC 引导稳定性帮助文件

*OC 0.6.6 正式版的配置文件新增和删除了若干条目，建议按照使用习惯重新配置。支持 macOS 11.2，可直接升级。有关启动项高优先级的使用方法有所改变，详见 [Q&A 条目 7](#7-如何使用-oc-的启动项高优先级功能)。*

#### 2021.01.16
* 更新 OpenCore 至 0.6.5 正式版
* 更新 AppleALC \ WhateverGreen \ IntelMausi \ CPUFriend Kexts 至官方最新版
* 更新 OpenRuntime \ OpenCanopy 驱动
* 更新`/EFI/OC/Resources`启动主题相关文件

*OC 0.6.5 正式版的配置文件仅新增了 Misc > Boot > PickerVariant 和 UEFI > Audio > SetupDelay 两个条目、删除 UEFI > Quirks > DeduplicateBootOrder 一个条目，同时对若干条目进行排序（使用无差别），建议直接手动更新。*

</details>

<details><summary>2020 年更新记录</summary>

#### 2020.12.18
* 更新 OpenCore 至 0.6.4 正式版
* 更新 Lilu \ AppleALC \ WhateverGreen \ VitualSMC Kexts 至官方最新版，更新 USBInjectAll Kext 为更新的修改版
* 更新 OpenRuntime \ OpenCanopy 驱动
* 移除 SSDT-HCMC SSDT 文件

*OC 0.6.4 正式版的配置文件新增和删除了若干条目，建议按照使用习惯重新配置。支持 macOS 11.1，可直接升级（因近期事务繁多，拖到今天才得以更新，为等待的用户道一声抱歉）。*

#### 2020.11.12
* 更新 OpenCore 至 0.6.3 正式版
* 更新 Lilu \ AppleALC \ WhateverGreen \ VitualSMC Kexts 至官方最新版
* 更新 OpenRuntime \ OpenCanopy 驱动

*OC 0.6.3 正式版的配置文件仅新增了 Kernel > Quirks > ForceSecureBootScheme、PlatformInfo > CustomMemory 和 UEFI > Output > ForceResolution 三个条目，建议直接手动添加。支持 ~~bugOS~~macOS Big Sur 11.0 RC 版，详见 [Q&A 条目 9](#9-如何使用-macos-big-sur-11)。*

#### 2020.10.10
* 更新 OpenCore 至 0.6.2 正式版
* 更新 Lilu \ AppleALC \ WhateverGreen \ IntelMausi \ VitualSMC \ CPUFriend Kexts 至官方最新版
* 更新 OpenRuntime \ OpenCanopy 驱动
* 添加`/EFI/OC/Bootstrap/Bootstrap.efi`OC 引导稳定性帮助文件

*OC 0.6.2 正式版的配置文件新增和删除了若干条目，建议按照使用习惯重新配置。支持 macOS 10.15.7，可直接升级；支持 ~~bugOS~~macOS Big Sur 11.0 测试版，详见 [Q&A 条目 9](#9-如何使用-macos-big-sur-11)。有关 Bootstrap 的使用详见 [Q&A 条目 8](#8-如何使用-oc-的启动项高优先级功能)。*

#### 2020.09.16
* 更新 OpenCore 至 0.6.1 正式版
* 更新 Lilu \ AppleALC \ WhateverGreen \ VitualSMC Kexts 至官方最新版
* 更新 OpenRuntime \ OpenCanopy 驱动

*OC 0.6.1 正式版的配置文件新增和删除了若干条目，建议按照使用习惯重新配置。支持 ~~bugOS~~macOS Big Sur 11.0 测试版，详见 [Q&A 条目 9](#9-如何使用-macos-big-sur-11)。*

#### 2020.08.07
* 更新 OpenCore 至 0.6.0 正式版
* 更新 Lilu \ AppleALC \ WhateverGreen \ VitualSMC \ CPUFriend Kexts 至官方最新版
* 更新 OpenRuntime \ OpenCanopy 驱动

*OC 0.6.0 正式版的配置文件新增和删除了若干条目，建议按照使用习惯重新配置。支持 macOS 10.15.6，可直接升级；支持 ~~bugOS~~macOS Big Sur 11.0 测试版，详见 [Q&A 条目 9](#9-如何使用-macos-big-sur-11)。*

#### 2020.06.16
* 更新 OpenCore 至 0.5.9 正式版
* 更新 Lilu \ AppleALC \ IntelMausi \ WhateverGreen \ VitualSMC Kexts 至官方最新版，更新 USBInjectAll kext 为更新的修改版
* 更新 OpenRuntime \ OpenCanopy 驱动，移除 ApfsDriverLoader 驱动
* 更新`/EFI/OC/Resources`启动主题相关文件

*OC 0.5.9 正式版的配置文件新增和删除了若干条目，建议按照使用习惯重新配置。支持 macOS 10.15.5，可直接升级（因近期事务繁多，拖到今天才得以更新，为等待的用户道一声抱歉）。*

#### 2020.04.12
* 更新 OpenCore 至 0.5.7 正式版
* 更新 Lilu \ AppleALC \ WhateverGreen \ VitualSMC Kexts 至官方最新版
* 替换 FwRuntimeServices 驱动为 OpenRuntime 驱动，添加 OpenCanopy 驱动
* 替换 Shell 工具为 OpenShell 工具
* 添加`/EFI/OC/Resources`主题相关文件夹，其中 Font \ Image \ Label 目录包含文件
* 开启 KASLR 内存注入，添加 igfxfw=2 启动参数

*OC 0.5.7 正式版的配置文件新增和删除了若干条目，建议按照使用习惯重新配置。添加启动主题但默认未启用，如需使用可将配置文件 Misc > Boot > Picker 的 Builtin 修改为 External；igfxfw=2 启动参数可以满频使用核显，如果没有核显可将其移除（因近期事务繁多，拖到今天才得以更新，为等待的用户道一声抱歉）。*

#### 2020.03.03
* 更新 OpenCore 至 0.5.6 正式版
* 更新 Lilu \ AppleALC \ WhateverGreen Kexts 至官方最新版
* 更新 ApfsDriverLoader \ HfsPlus \ FwRuntimeServices 驱动至最新版
* 添加 ExFatDxe 驱动，同步添加配置文件 EFI > Drivers > 2: ExFatDxe.efi
* 更新 Shell \ VerifyMsrE2 工具至最新版
* 移除`/EFI/OC/Tools/memtest.efi`文件，同步移除配置文件 Misc > Tools > 2 条目

*OC 0.5.6 正式版的配置文件新增和删除了若干条目，建议按照使用习惯重新配置。目前已支持 ~~bugOS~~macOS 10.15.4，正式版发布后可直接升级。*

#### 2020.02.14
* 移除 Slide=129 启动参数（相关 [Issue](https://github.com/GeQ1an/MSI-B360M-MORTAR-HACKINTOSH-OPENCORE-EFI/issues/7)）
* 删除`/EFI/OC/Drivers/AppleUsbKbDxe.efi`文件（无用，详见 [vit9696 的解释](https://applelife.ru/threads/opencore-obsuzhdenie-i-ustanovka.2944066/page-176#post-856653)）
* 修改`/EFI/OC/Drivers/HFSPlus.efi`文件名称为`HfsPlus.efi`，同步修改配置文件 UEFI > Drivers > 2 为 HfsPlus.efi（无实质作用，仅统一名称格式）

#### 2020.02.10
* 修复 OpenCore 0.5.5 正式版将 SupportCsm 改名为 AdviseWindows 我却没有更改配置文件的问题

*请手动更改该项名称（PlatformInfo > Generic），并建议按照官方示例文件调整 AdviseWindows 顺序至 Generic 第一位。*

#### 2020.02.05
* 设置 TakeoffDelay 参数为 200 (Misc > Boot，单位：毫秒) 以支持引导过程的原生快捷键

*实测参数设置到 150 时便可触发原生快捷键，但触发概率较小，200 是较为均衡的数值，可将其适当调高，如 300~500 之间。在 OC 0.5.5 版本之前，我一直无法触发原生快捷键 (可能和键盘有关？)，如果你之前能触发，或仍不能触发，请在 Issues 讨论。*

#### 2020.02.04
* 更新 OpenCore 至 0.5.5 正式版
* 更新 AppleALC \ VitualSMC Kexts 至官方最新版
* 添加 UEFI Shell 工具（默认未启用）

*OC 0.5.5 正式版的配置文件新增了若干条目，建议按照使用习惯重新配置。*

#### 2020.02.02
* 更新支持读写硬件 NVRAM，不再需要模拟 NVRAM

*如之前进行过模拟 NVRAM 操作，请在`终端`执行下面两条命令后，删除`/EFI/nvram.plist`文件。*<br>
```
sudo rm -rf $(sudo defaults read com.apple.loginwindow LogoutHook) //删除 LogoutHook
sudo defaults delete com.apple.loginwindow LogoutHook  //清空 LogoutHook 的触发设置
```

#### 2020.01.14
* 更新 OpenCore 至 0.5.4 正式版
* 更新 Lilu \ AppleALC \ CPUFriend \ VitualSMC \ WhateverGreen Kexts 至官方最新版
* 移除`/EFI/OC/Drivers/virtualsmc.efi`文件（已被合并至 OC 中）

*OC 0.5.4 正式版的配置文件新增了若干条目，建议按照使用习惯重新配置。*

#### 2020.01.05
* 使用 OpenCore 官方补丁间接修复「不开启小憩无法进入睡眠」的问题，移除 SSDT-SBUS.aml 文件

*不开启小憩的目的是睡眠后不被自动唤醒，开启 OC 的「禁用 RTC 唤醒计划」补丁后，打开小憩功能可以正常进入睡眠，且不会被自动唤醒，间接达到「不开启小憩进入睡眠」的状态，如不需要可以手动关闭该补丁（感谢 [ArchFeh](https://github.com/GeQ1an/MSI-B360M-MORTAR-HACKINTOSH-OPENCORE-EFI/issues/5) 针对文案的提醒）。*<br>
![](https://raw.githubusercontent.com/GeQ1an/MSI-B360M-MORTAR-HACKINTOSH-OPENCORE-EFI/master/Images/Explain/ProperTree_Kernel_Patch.png)

</details>

<details><summary>2019 年更新记录</summary>

#### 2019.12.29
* 更新 WhateverGreen.kext 至 1.3.6 最新编译版
* 修复「不开启小憩无法进入睡眠」的问题（理论上不该存在问题）

#### 2019.12.23
* 更新 WhateverGreen.kext 至 1.3.6
* 修改 shikigva 启动参数代码为 80（支持 Safari 硬解 DRM 内容）

#### 2019.12.20
* 上传忘记添加的 SSDT-SBUS.aml（用来修复「不开启小憩无法进入睡眠」，具体效果待测试）

#### 2019.12.19
* 经过三天的测试后，上传第一版

</details>

## 使用 EFI
准备 [ProperTree](https://github.com/corpnewt/ProperTree) ([下载](https://github.com/GeQ1an/Personal/raw/master/Hackintosh/ProperTree.zip)) 或 [PlistEdit Pro](https://www.fatcatsoftware.com/plisteditpro/) 编辑配置文件，尽量避免使用其他编辑器。<br>
OpenCore 拥有高度的可定制化，建议先参考下面的说明使用配置好的基础版本，之后再通过 [xjn 博客](https://blog.xjn819.com/?p=543) 和 [黑果小兵博客](https://blog.daliansky.net/OpenCore-BootLoader.html) 学习更多内容进行修改。

### BIOS 设置
*请先确定正在使用的 BIOS 版本，[迫击炮](https://cn.msi.com/Motherboard/support/B360M-MORTAR) 7B23v16 以上，[迫击炮钛金版](https://cn.msi.com/Motherboard/support/B360M-MORTAR-TITANIUM) 7B23vA6 以上，否则请参考官方文档升级 BIOS 至最新版本（v19 & vA9 版本测试可用）。*<br>

<details><summary>SETTINGS</summary>

  - 高级
    - PCI子系统设置
      - Above 4G memory/Crypto Currency mining [**允许**]
    - ACPI设置
      - 电源 LED 灯 [**双色**] *(如果选择 [闪烁]，睡眠时电源灯将不断闪烁)*
    - 整合周边设备
      - SATA设置
        - SATA模式 [**AHCI模式**] *(如果选择 Optane 模式将无法识别 SATA 硬盘)*
    - 内建显示配置
      - 设置第一显卡 [**PEG**] *(仅同时拥有核显及独显需要手动设置)*
      - 集显共享内存 [**64M**] *(如果使用拥有核显的处理器)*
      - 集成显卡多显示器 [**允许**] *(如果使用拥有核显的处理器)*
    - USB设置
      - XHCI Hand-off [**允许**]
      - 传统USB支持 [**允许**]
    - 电源管理设置
      - ErP Ready [**允许**]
      - USB Standby Power at S4/S5 [**允许**]
    - Windows操作系统的配置
      - Windows 10 WHQL支持 [**允许**] *(开启为「纯」UEFI 模式，否则为「兼容」UEFI 模式，推荐设置为允许)*
      - MSI 快速开机 [**禁止**]
      - 快速开机 [**禁止**]
    - 唤醒事件设置
      - 唤醒事件管理 [**BIOS**]
      - USB设备从S3/S4/S5唤醒 [**允许**]
  - 启动
    - 启动NumLock状态 [**关**]*（macOS 默认可使用数字键盘，只有 macOS 的话推荐关闭）*
    - 启动模式选择 [**UEFI**]

</details>

<details><summary>OC(Overclocking)</summary>

  - CPU 特征
    - Intel 虚拟化技术 [**允许**] *(**必须!**)*
    - Intel VT-D 技术 [**禁止**] *(**必须!**)*
    - CFG锁定 [**禁止**] *(**必须!**)*

</details>

### 直接使用
适合**同时使用核显 + 独显**的用户。<br>
下载整包后，如果之前在 Clover 时就使用`iMac19,1`机型，可直接使用之前的三码，或使用 [Hackintool](https://github.com/headkaze/Hackintool/releases) （其他工具亦可）选择`iMac19,1`机型生成新的三码 + ROM，用 ProperTree 打开`/EFI/OC/config.plist`配置文件，填入到 PlatformInfo > Generic 位置中（如下图）。<br>
![](https://raw.githubusercontent.com/GeQ1an/MSI-B360M-MORTAR-HACKINTOSH-OPENCORE-EFI/master/Images/Explain/ProperTree_PlatformInfo.png)
<br>
保存后，先通过 USB 测试引导，无问题后再将 EFI 文件夹放置到启动磁盘 EFI 分区，重启电脑。

### 无核显使用
适合**只使用独显**的用户。<br>
1. 填入`iMacPro1,1`机型的三码 + ROM 信息到`/EFI/OC/config.plist`配置文件 PlatformInfo > Generic 处，并将机型修改为`iMacPro1,1`。<br>
2. 删除`/EFI/OC/config.plist`配置文件 DeviceProperties > Add > PciRoot(0x0)/Pci(0x2,0x0) 这一行参数（如下图）。<br>
![](https://raw.githubusercontent.com/GeQ1an/MSI-B360M-MORTAR-HACKINTOSH-OPENCORE-EFI/master/Images/Explain/ProperTree_DeviceProperties.png)
<br>
保存后，先通过 USB 测试引导，无问题后再将 EFI 文件夹放置到启动磁盘 EFI 分区，重启电脑。

### 无独显使用
适合**只使用核显**的用户。<br>
1. 填入`Macmini8,1`机型的三码 + ROM 信息到`/EFI/OC/config.plist`配置文件 PlatformInfo > Generic 处，并将机型修改为`Macmini8,1`。<br>
2. 修改`/EFI/OC/config.plist`配置文件 DeviceProperties > Add > PciRoot(0x0)/Pci(0x2,0x0) 下 AAPL,ig-platform-id 参数为`07009b3e`，并新增 device-id 参数为`9B3E0000`，新增 framebuffer-unifiedmem 参数为`00000080`，新增 framebuffer-patch-enable 参数为`01000000`（如下图）。<br>
![](https://raw.githubusercontent.com/GeQ1an/MSI-B360M-MORTAR-HACKINTOSH-OPENCORE-EFI/master/Images/Explain/ProperTree_DeviceProperties_I.png)
<br>
保存后，先通过 USB 测试引导，无问题后再将 EFI 文件夹放置到启动磁盘 EFI 分区，重启电脑。

### 对于 RX 5000 \ RX 6000 系列显卡
目前 RX 5000 系列 Navi 10 核心显卡、RX 6000 系列 Navi 21 核心显卡和 RX 6000 系列 Navi 23 核心显卡均应该手动添加`agdpmod=pikera`启动参数来防止开机黑屏，目前暂无其他解决方法。

### 进阶使用
1. 参考 [黑果小兵博客](https://blog.daliansky.net/Intel-FB-Patcher-USB-Custom-Video.html) 生成`USBPorts.kext`USB 定制文件，放入`/EFI/OC/Kexts/`替换同名文件，打开`/EFI/OC/config.plist`，关闭 Kernel > Add > 7，打开 8。<br>
   ![](https://raw.githubusercontent.com/GeQ1an/MSI-B360M-MORTAR-HACKINTOSH-OPENCORE-EFI/master/Images/Explain/ProperTree_Kernel_USB.png)
   *目录内有我的 USB 定制文件，可在备份好自己 EFI 的情况下尝试使用。SMBIOS 为 iMac19,1，若你使用其他机型需自行打开 USBPorts.kext/Contents/Info.plist 修改 IOKitPersonalities > iMac19,1-XHC 和 model 子参数中的 iMac19,1 为你的机型 (两个 iMac19,1 字符都需要修改)；若你需要取消 HS07 内建，打开 Info.plist 修改 IOKitPersonalities > iMac19,1-XHC > IOProviderMergeProperties > ports > HS07 > UsbConnector 参数为 0 即可。端口具体定制情况如下：*<br>
   
   <details><summary>点击展开查看</summary>
   
   ```
   1.  HS01 - Internal - 主板 USB 2.0 接口 - 蓝牙
   2.  HS03 - Internal - 背板顶部 USB 2.0  - 鼠标
   3.  HS04 - Internal - 背板顶部 USB 2.0  - 键盘
   4.  HS05 - U S B  3 - 背板右下 USB 3.1 Type-A (对应 SS01)
   5.  HS06 - TypeC+Sw - 背板左下 USB 3.1 Type-C (对应 SS02)
   6.  HS07 - Internal - 背板左上 USB 2.0  - 摄像头
   7.  HS08 - U S B  2 - 背板右上 USB 2.0
   8.  HS09 - U S B  3 - 前置 USB 3.0 (对应 SS05)
   9.  HS10 - U S B  3 - 前置 USB 3.0 (对应 SS06)
   10. SS01 - U S B  3 - 背板右下 USB 3.1 Type-A
   11. SS02 - TypeC+Sw - 背板左下 USB 3.1 Type-C
   12. SS05 - U S B  3 - 前置 USB 3.0
   13. SS06 - U S B  3 - 前置 USB 3.0
   ```
   
   </details>

2. 参考 [xjn 博客](https://blog.xjn819.com/?p=543) 的进阶部分「4.1 CPU 的变频优化」或 xjn 大佬发表于 PCbeta 的帖子 [FCPX 核显独显全程满速指南](http://bbs.pcbeta.com/viewthread-1836920-1-1.html) 中「HWP 变频」部分，根据个人需求定制`CPUFriendDataProvider.kext`HWP 变频文件，放入`/EFI/OC/Kexts/`替换同名文件，启用`/EFI/OC/config.plist`文件 Kernel > Add > 10 和 11。<br>
   ![](https://raw.githubusercontent.com/GeQ1an/MSI-B360M-MORTAR-HACKINTOSH-OPENCORE-EFI/master/Images/Explain/ProperTree_Kernel_CPU.png)
   *iMac19,2 和 iMacPro1,1 均不支持 HWP 变频，无需尝试。对于有核显的用户建议选择 iMac19,1 机型，对于只使用核显的用户推荐 Macmini8,1 机型。目录内附带的是本人按照个人习惯定制的 9600K HWP 变频文件，不建议直接启用，更不建议其他处理器用户启用。*

## Q&A
#### 1. 开机时苹果 logo 显示不正常怎么办？
   有两个方法可以解决这个问题。<br>
   方法一：在`/EFI/OC/config.plist`配置文件 UEFI > Output > Resolution 处填写正确的显示器分辨率；<br>
   方法二：将 BIOS「STTINGS\启动\全荧幕商标」设置为 [允许]。<br>
   两种方法选择其一即可，如果同时使用的话开机 logo 的显示依旧会不正常，原本更推荐方法二（会比方法一进入系统登陆界面略快一些），但反复测试后发现，如果在 BIOS 打开「Windows 10 WHQL支持」，使用方法二可能会导致**关机再开机时丢失苹果 logo**，请测试后选择~~适合~~自己喜欢的方法。<br>
   **P.S.** 目前 OC 已支持自动检测 HiDPI，如果你使用 2K 及以下分辨率无法开启 HiDPI 的显示器且开机时显示不正常，请尝试将配置文件 UEFI > Output > UIScale 设置为`01`。
#### 2. 无法正常进入睡眠状态怎么办？
   目前所知的情况是 ~~bugOS~~macOS 10.15 至 10.15.7（包括补充更新版本）都存在睡眠相关 bugs，需要在节能中打开 “启用电能小憩” 选项才可正常进入睡眠。<br>
   一般而言，系统更新到 macOS 11 Big Sur 和 macOS 12 Monterey 以后可在不打开 “启用电能小憩” 选项的情况下正常进入睡眠。
#### 3. 为什么推荐拥有核显的 CPU？
   首先，macOS Catalina 原生支持 4K 双硬解的独显最低为 RX VEGA⁵⁶，而第七代及以后的酷睿处理器核显可以和低于 RX VEGA⁵⁶ 的独显协同工作，完成 4K 双硬解；<br>
   其次，因为黑果没有 T2 芯片，所以没有核显的黑果无法使用随航（Sidecar）功能。
#### 4. 引导过程触发原生快捷键怎么这么难？
   我也被这个问题困扰了许久，在 OC 0.5.5 之前尝试过各种配置组合，均无法触发，但 OC 更新 0.5.5 后，通过设置 TakeoffDelay 参数可在引导过程中触发原生快捷键，建议在启动时按住组合键，或键盘灯亮起时不断重按组合键，可自行调整 TakeoffDelay 参数。
#### 5. NVMe 硬盘温度过高怎么办？
   一般来说读写速度越快的硬盘温度往往越高，无需太过担心，但待机情况下超过 50℃ 或你认为硬盘的温度不正常，可尝试加载 [NVMeFix](https://github.com/acidanthera/NVMeFix/releases) 解决。<br>
   将 NVMeFix.kext 放入`/EFI/OC/Kexts/`目录，打开 OC 配置文件，在 Kernel > Add 处添加 NVMeFix.kext（参考其他 kext 的添加方式），当前已添加并启用。
#### 6. 可以观看 Apple TV+ / Netflix 等 DRM 媒体吗？`更新！`
   得益于 WhateverGreen 的功能，添加 shikigva=80 启动参数后，拥有独立显卡的机器都可以直接使用 tv 应用，并观看 Apple TV+，也支持 Safari 硬解观看 Netflix / Amazon Prime 等流媒体。<br>
   macOS 10.15.4 之前版本，RX 4XX/5XX 大部分显卡不可使用 Safari 硬解 DRM（表现为冻屏），但这一问题在 10.15.4 中已经被修复，直接升级系统即可。<br>
   WhateverGreen 的 DRM 补丁目前不支持 Safari 14 和 macOS 11 及以后版本，但可以在`终端`中依次执行下列代码后正常使用 tv 应用观看 Apple TV+（Safari 仍然不可以正常解码 DRM）。
   ```
   defaults write com.apple.AppleGVA gvaForceAMDKE -bool YES
   defaults write com.apple.AppleGVA gvaForceAMDAVCEncode -bool YES
   defaults write com.apple.AppleGVA gvaForceAMDAVCDecode -bool YES
   defaults write com.apple.AppleGVA gvaForceAMDHEVCDecode -bool YES
   ```
   *注意：因为缺少 Apple Firmware，导致 iGPU 无法硬解 DRM，所以没有独显的机器无法观看 DRM 媒体。*
#### 7. 如何使用 OC 的启动项高优先级功能？
   ~~开启该功能后可能会造成无法设置 “启动磁盘” 的问题，默认未启用。如需启用该功能，请自行修改配置文件 Misc > Security > BootProtect 参数为`Bootstrap`（填写`None`为关闭）。仅适用于 OC 0.5.9 至 0.6.5 版本。~~<br>
   自 OC 0.6.6 版本开始，可通过修改配置文件 Misc > Boot > LauncherOption 参数为`Full`置顶 OC 启动项，填写`Disabled`则为默认不做改动。
#### 8. 如何使用 macOS Big Sur 11？
   请确认你的 OpenCore 已更新到 0.6.1 以上版本，且所有 Kexts 也已更新到最新版，将配置文件 Kernel > Quirks > DisableLinkeditJettison 设置为`Ture/Yes`即可。
#### 9. 为什么要开启安全启动和 SIP？
   首先，从 Monterey 开始，不会向未启用安全启动的包含 T2 芯片的 Mac 提供更新，所以需要我们打开安全启动功能，修改 OC 的 SecureBootModel 和 DmgLoading 两个设置。*（注：如果你使用不包含 T2 芯片的 iMac19,1 或 iMac19,2 SMBIOS，也可以选择关闭安全启动，请同步修改配置文件 Misc > Security > SecureBootModel 为`Disabled`、DmgLoading 为`Any`。）*<br>
   其次，从 Big Sur 开始，未开启 SIP 可能无法检测到更新，为了保证正常检测系统更新，需要修改 csr-active-config 设置开启 SIP ，开启 AllowToggleSip 选项后可在引导选择界面快速开关 SIP。如果更新此次 OC 后无法检测到更新可尝试到引导选择界面再次开启 SIP 解决问题（括号会标注状态，Enable 为开启，Disable 为关闭）。<br>
   详情参考 [OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/extras/monterey.html#ota-updates) 中的说明。
#### 10. 为什么使用 Catalina 需要额外修改配置？
   从 OpenCore 0.7.2 版本开始，早期的 APFS 驱动不会被加载（出于安全性考虑），这会导致低于 Big Sur 11.0 版本的系统无法启动，如果要启动 Catalina 或更早版本的系统，请修改配置文件 UEFI > APFS 下面的 MinDate 和 MinVersion 为`-1`，详情参考 [OC 0.7.2 版本](https://github.com/acidanthera/OpenCorePkg/releases/tag/0.7.2) 中的文档。
#### 11. 为什么一定要定制 USB？
   从 macOS Big Sur 11.3.1 开始，macOS 会使 OC 解除 15 个 USB 端口的 XhciPortLimit Quirk 失效，导致即使加载 USBInjectAll Kext 也无法全部正确加载超过 15 个的 USB 端口，可自行搜索 USB 定制教程或参考 [进阶使用](#进阶使用) \ [OpenCore Post Install](https://dortania.github.io/OpenCore-Post-Install/usb/) \ [黑苹果星球](https://heipg.cn/tutorial/customize-usb-port-windows.html)（包含 Windows 版，需付费查看，无相关利益）中有关 USB 定制的教程。
#### 12. 待更新

## 结语
完成以上步骤后，基本上已经有了一个完成度为 99% 的黑苹果设备，更多截图请查看 [截图预览](https://github.com/GeQ1an/MSI-B360M-MORTAR-HACKINTOSH-OPENCORE-EFI/tree/master/Images/Preview.md) 。<br>
<br>
黑果毕竟不是白果，内核补丁和新系统可能存在兼容性问题，使用一旦稳定后，追新速度不要太快，待各路大佬测试、完善后再升级也不迟。

## 鸣谢
[xjn](https://blog.xjn819.com/)<br>
[andot](https://github.com/andot/MSI-B360M-MORTAR-IMACPRO-EFI/)<br>
[daliansky](https://github.com/daliansky) ([黑果小兵](https://blog.daliansky.net/))<br>
[tonymoses](http://bbs.pcbeta.com/viewthread-1835637-1-1.html)<br>
[cattyhouse](https://github.com/cattyhouse/oc-guide/)<br>
[osx86zh](https://t.me/osx86zh/) ([Telegram](https://telegram.org/) 讨论组)<br>
[OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/)<br>
[derbalkon](https://github.com/derbalkon/B360M-CoffeeLake-Hackintosh/)<br>
[黑苹果星球](https://heipg.cn/)

## 链接
OpenCorePkg [官方版本](https://github.com/acidanthera/OpenCorePkg/releases) [自动编译](https://github.com/hjp521/OpenCore-Factory/releases) / [Lilu](https://github.com/acidanthera/Lilu/releases) / [AppleALC](https://github.com/acidanthera/AppleALC/releases) / [WhateverGreen](https://github.com/acidanthera/WhateverGreen/releases) / [IntelMausi](https://github.com/acidanthera/IntelMausi/releases) / [VirtualSMC](https://github.com/acidanthera/VirtualSMC/releases) / [CPUFriend](https://github.com/acidanthera/CPUFriend/releases) / [NVMeFix](https://github.com/acidanthera/NVMeFix/releases) / [OcBinaryData](https://github.com/acidanthera/OcBinaryData) / [MaciASL](https://github.com/acidanthera/MaciASL/releases) / [ProperTree](https://github.com/corpnewt/ProperTree) / [Hackintool](https://github.com/headkaze/Hackintool/releases) / [HWMonitorSMC2](https://github.com/CloverHackyColor/HWMonitorSMC2/releases)

## 写在最后
**警告：使用此 EFI 非法获利的小站，请尽快停止违法行为，改为免费向用户提供并注明出处。**<br>
<br>
有问题可以在 [Issues](https://github.com/GeQ1an/MSI-B360M-MORTAR-HACKINTOSH-OPENCORE-EFI/issues) 反馈，或直接通过 [Telegram](https://t.me/GeQ1an) 联系我，确定问题后将及时修复此 EFI，但作为**免费分享**的项目，本人**没有义务**解答各种令人无奈的问题，也不对修复 EFI 问题的**时效**做出保证，**伸手党也该适可而止**。<br>
<br>
如果你觉得我的工作帮助到了你，可以选择进行打赏，这将是我不断完善 EFI 的动力。<br>
`#吱口令#长按复制此条消息，去支付宝首页进行搜索粘贴即可给我打赏9Rgv0b74jI#`
![](https://raw.githubusercontent.com/GeQ1an/Rules/master/Images/Pay2Me.png)<br>
<br>
另外，如果有在 iOS 使用 Quantumult X 的用户，欢迎使用我的规则 [Stick Rules](https://github.com/GeQ1an/Rules/tree/master)，也欢迎 [点击此处](https://t.me/usestick) 订阅我的 Telegram 频道及时获取规则和 EFI 相关信息。
