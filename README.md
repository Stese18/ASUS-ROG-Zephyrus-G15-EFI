# ASUS-ROG-Zephyrus-G15-EFI
### ASUS ROG Zephyrus G15 EFI-Running on Sonoma
### 配置为：参考下图
![1698993814009](https://github.com/Stese18/ASUS-ROG-Zephyrus-G15-EFI/assets/134680522/33406b6f-dceb-47bf-b564-3e60e867be11)
由于AMD核显驱动（NootedRed）无法在安装前正常运行，所以我们只能自己手动关闭核显驱动
##### 修改EFI，Config
##### 推荐使用工具[OCAT](https://github.com/ic005k/OCAuxiliaryTools)
![image](https://github.com/Stese18/ASUS-ROG-Zephyrus-G15-EFI/assets/134680522/850c5c5f-c11b-40e9-8931-6a6835adce47)
把Nootedred关闭（状态修改为false）
#### 目前版本
目前使用macOS 14.1
##### 系统截图
![截屏2023-11-03 01 12 58](https://github.com/Stese18/ASUS-ROG-Zephyrus-G15-EFI/assets/134680522/f404a709-bcee-40a6-a47e-944367bbf391)
![截屏2023-11-03 01 12 38](https://github.com/Stese18/ASUS-ROG-Zephyrus-G15-EFI/assets/134680522/8ea7b062-26d5-433b-b8a7-052c08a8a272)
![截屏2023-11-03 01 18 22](https://github.com/Stese18/ASUS-ROG-Zephyrus-G15-EFI/assets/134680522/be164355-f13e-45e0-a8bc-2c608688f178)
![截屏2023-11-03 01 13 13](https://github.com/Stese18/ASUS-ROG-Zephyrus-G15-EFI/assets/134680522/b55865d6-7d8d-44b1-8fec-c4e4f9279093)

理论上支持macOS 13
## 什么可用
核显

声卡 ALC285(ID为66)

触控板 I2C

USB全接口无需屏蔽XHCI

电池

正常开关机

## 无法驱动
有线网卡（型号为Realtek Gaming GBE RTL8162)

无线网卡（默认型号为MediaTek Wi-Fi 6 MT7921 Wireless LAN Card)

外接（双雷电走的是独立显卡）

独立显卡（RTX3070不被苹果支持）

睡眠（AMD笔记本大部分的通病）
## 额外
由于机器默认硬盘为HFM001TD3JX013N海力士，所以如果直接安装会导致Ionvme报错

所以我们需要把内置硬盘屏蔽（默认已经添加屏蔽SSDT）

如果你想直接用默认接口，那就需要把我载入的SSDT取消，下面是方法
##### 推荐使用工具[OCAT](https://github.com/ic005k/OCAuxiliaryTools)
![image](https://github.com/Stese18/ASUS-ROG-Zephyrus-G15-EFI/assets/134680522/45d3638e-b033-4526-b0fb-4ed69d0e018a)

GPP6为此机器的默认NVME接口，可以看到默认是启用状态，所以我们需要跟关闭核显驱动一样

把他关闭（状态修改为false），如果你想换硬盘位置或者新硬盘位置有新的不支持硬盘想屏蔽

那就把GPP5的SSDT开启（状态修改为true）
### 警告
## EFI原作者为白给大老师（Stese18)第三方转发需要打上原作者名称
