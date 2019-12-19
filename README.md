# 微星 B360M 迫击炮（钛金版）黑苹果 OpenCore EFI

## EFI 介绍
此 EFI 使用 `iMac19,1` 机型，核显 + 独显共同硬解，默认启用全部 USB 端口，[OpenCore](https://github.com/acidanthera/OpenCorePkg) 版本：0.5.4<br>
<br>
![](https://raw.githubusercontent.com/GeQ1an/MSI-B360M-MORTAR-HACKINTOSH-OPENCORE-EFI/master/Images/About.png)

### 可用功能
- [x] 声卡（板载）/ 网卡（板载）
- [x] 显卡（核显 + 独显）/ 硬解 4K（HEVC + H.264）
- [x] WiFi（PCI-E 设备） / 蓝牙（PCI-E 设备）
- [x] 隔空投送 / 接力 / 随航
- [x] FaceTime / iMessage
- [x] Apple Music / Apple TV Plus
- [x] 睿频 / HWP 变频 / 原生电源管理
- [x] 睡眠 / 键盘、鼠标唤醒
- [x] 其他白果功能（99%）

### 我的配置

|         硬件       |                   型号                     | 
|-------------------:|:------------------------------------------|
|               主板 | 微星 B360M 迫击炮                               |
|             处理器 | 英特尔酷睿 i5-9600K                            |
|               显卡 | 公版 RX570 4GB（由微星代工）                    |
|               硬盘 | 西部数据 SN750 500GB                          |
|               内存 | 光威悍将 DDR4 2666Mhz 8GB x 2                 |
|        无线 + 蓝牙 | 奋威 BCM94360CD（双频 1750M + 蓝牙 4.0）PCI-E 无线网卡  |
|  机箱 + 电源 + 散热 | 乔思伯 U3 + 台达 NX450 + 九州风神玄冰 400 + ARCTIC F12 PWM |
|             显示器 | 飞利浦 276E8VJSB（27 英寸 4K 分辨率）                 |
|     摄像头 + 麦克风 | 双飞燕 PK-838G 带麦克风摄像头                       |
|               音箱 | 漫步者 R19U 2.0 迷你音箱                           |
|               键盘 | iQunix F96 珊瑚海（有线茶轴 RGB 版）                 |
|               鼠标 | 罗技 MX Anywhere 2（使用优联连接，以方便在 BIOS 中使用）   |

### 兼容的配置

|         硬件       |                              型号                           | 
|-------------------:|:------------------------------------------------------------|
|               主板 | 微星 B360M 迫击炮（钛金版）                                    |
|             处理器 | 英特尔第 8 代、第 9 代酷睿处理器（推荐拥有核显的版本）             |
|               显卡 | RX560、RX570、RX580、RX590、Vega56、Vega64、RX 5700、RX 5700 XT |
|               硬盘 | 除了几个特例（自行查询），其他的基本都可以                         |
|               内存 | 除了非常差的，基本都可以                                        |
|        无线 + 蓝牙 | 黑苹果免驱版无线 + 蓝牙的 PCI-E 卡都可以                          |
|     摄像头 + 麦克风 | macOS 免驱版都可以                                             |
|  机箱 + 电源 + 风扇 | 根据个人爱好和 CPU、显卡的功率来决定                               |
|             显示器 | 根据个人爱好选择（推荐 4K 分辨率）                                |
|  键盘 + 鼠标 + 音箱 | 根据个人爱好选择                                                |
|           其它外设 | 根据个人爱好选配                                              |

*显卡优先选择蓝宝石，其次选择迪兰恒进、华硕和微星，避开 RX580 2048SP 版本！*

## 使用 EFI
准备 [ProperTree](https://blog.xjn819.com/wp-content/uploads/2019/10/ProperTree.zip) 用来编辑配置文件，请勿使用其他编辑器编辑（切记）。<br>
OpenCore 拥有高度的可定制化，建议先参考下面的说明使用配置好的基础版本，之后再通过 [xjn 博客](https://blog.xjn819.com/?p=543) 和 [黑果小兵博客](https://blog.daliansky.net/OpenCore-BootLoader.html) 学习更多内容进行修改。

### BIOS 设置
请先确定正在使用的 BIOS 版本，[迫击炮](https://cn.msi.com/Motherboard/support/B360M-MORTAR) 7B23v16 以上，[迫击炮钛金版](https://cn.msi.com/Motherboard/support/B360M-MORTAR-TITANIUM) 7B23vA6 以上，如不符合请先升级 BIOS 版本。<br>
打开如下功能<br>

关闭如下功能<br>

### 直接使用
仅适合 9600K 处理器的用户使用！<br>
下载整包后，如果之前在 Clover 时就使用 `iMac19,1` 机型，可直接使用之前的三码，或使用 [Clover Configurator](https://mackie100projects.altervista.org/download-clover-configurator/) 选择 `iMac19,1` 机型生成新的三码 + ROM，用 ProperTree 打开 `EFI/OC/config.plist` 文件，填入到 PlatformInfo > Generic 位置中（如下图）。
![](https://raw.githubusercontent.com/GeQ1an/MSI-B360M-MORTAR-HACKINTOSH-OPENCORE-EFI/master/Images/ProperTree_PlatformInfo.png)
保存后，将 EFI 文件夹直接放置到已经清空的 EFI 分区，重启电脑。

### 修改使用
使用其他拥有核显处理器的用户，除了需要填入三码等信息外，还需要将 `EFI/OC/config.plist` 文件 Kernel > Add > 10 和 11 中 Enabled 的 Ture 手动修改为 False（如下图）。<br>
*这是 9600K 专用的 HWP 变频文件，其他处理器不可启用！*
![](https://github.com/GeQ1an/MSI-B360M-MORTAR-HACKINTOSH-OPENCORE-EFI/blob/master/Images/ProperTree_Kernel.png)
保存后，将 EFI 文件夹直接放置到已经清空的 EFI 分区，重启电脑。

### 无核显使用
打开 `EFI/OC/config.plist` 文件 PlatformInfo > Generic，将机型修改为 `iMacPro1,1` 填入相应机型的三码信息，并删除 DeviceProperties > Add > PciRoot(0x0)/Pci(0x2,0x0) 下 AAPL,ig-platform-id 这一行参数（如下图）。
![](https://raw.githubusercontent.com/GeQ1an/MSI-B360M-MORTAR-HACKINTOSH-OPENCORE-EFI/master/Images/ProperTree_DeviceProperties.png)

### 模拟 NVRAM
无论是直接使用还是修改使用，都建议参考 [xjn 博客](https://blog.xjn819.com/?p=543) 的完善部分，进行模拟 NVRAM 的操作。

### 进阶使用
1. 参考 [xjn 博客](https://blog.xjn819.com/?p=543) 的进阶部分生成 `CPUFriendDataProvider.kext` HWP 变频文件，放入 `EFI/OC/Kexts/` 替换同名文件，重新启用 `EFI/OC/config.plist` 文件 Kernel > Add > 10 和 11。
2. 参考 [黑果小兵博客](https://blog.daliansky.net/Intel-FB-Patcher-USB-Custom-Video.html) 生成 `USBPorts.kext` USB 定制文件，放入 `EFI/OC/Kexts/` 替换同名文件，打开 `EFI/OC/config.plist`，打开 Kernel > Add > 7 和 8，关闭 9。
![](https://github.com/GeQ1an/MSI-B360M-MORTAR-HACKINTOSH-OPENCORE-EFI/blob/master/Images/ProperTree_Kernel.png)

## 结语
完成以上步骤后，基本上已经有了一个完成度 99% 的黑苹果设备，更多截图请查看 [Image](https://github.com/GeQ1an/MSI-B360M-MORTAR-HACKINTOSH-OPENCORE-EFI/tree/master/Images) 。
黑果和白果不一样，一旦稳定后，系统等各个方面追新速度不要太快，待各路大佬测试后再升级也不迟。
