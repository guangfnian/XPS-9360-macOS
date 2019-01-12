# XPS 9360 hackintosh
目前在Mojave 10.14.2下正常使用

在[the-darkvoid](https://github.com/the-darkvoid/XPS9360-macOS)的基础上：
- 将VirtualSMC换回了FakeSMC
- 启动参数加入darkwake=no，以解决睡眠唤醒耳机无声的问题
- 加入参数alcid=11，驱动声卡
- 去除参数igfxcflbklt=opcode
- 机型修改为MBP15,2（修改为此机型后按此[issue](https://github.com/the-darkvoid/XPS9360-macOS/issues/96)操作来解决要求输密码时的延迟问题）

## 硬件配置
- Intel i7 8550u
- 16G RAM
- 闪迪A400 512G NVME SSD
- 夏普 SHP144A (LQ133Z1) 分辨率3200*1800
- 内置的无线网卡为killer 1535，更换为某宝上的拆机DW1560
- 声卡ALC256

## 准备&安装过程&注意事项
安装前请务必阅读[这篇guide](https://www.tonymacx86.com/threads/guide-dell-xps-13-9360-on-macos-sierra-10-12-x-lts-long-term-support-guide.213141/)和[the-darkvoid的repo](https://github.com/the-darkvoid/XPS9360-macOS)
下面仅举出其中一些注意事项。
- 确保BIOS版本和雷电固件均为最新。部分XPS可能会受CABC影响（即屏幕亮度会随显示内容调节，具体表现可参见[此视频](https://www.youtube.com/watch?v=uuE3a4AMq5w)），可根据[这篇](https://wiki.archlinux.org/index.php/Dell_XPS_13_(9360)#Content_Adaptive_Brightness_Control)来检测以及关闭CABC。所有工具均可在戴尔官网找到。
- **UEFI变量设置**。在Clover中进入UEFI Shell，利用命令`setup_var [offset] [value]`来设定offset的value值。需要设定的值[the-darkvoid](https://github.com/the-darkvoid/XPS9360-macOS)已经给出。**这点非常重要**。
- BIOS参考上述guide设置，主要是关闭大部分安全相关的选项以及intel VT-D，但需要注意的是，这篇guide里关闭了thunderbolt boot和pre-boot support，这样会导致雷电口无法正常使用（可充电、不可数据传输，外接显示器暂未测试），开启后正常（可充电、可数据传输，外接显示器暂未测试）
- 参考guide，非三星的nvme固态需要在Linux环境下使用nvme-cli工具4k对齐（这会抹掉所有数据）
- 其他待补充
## 问题
- 开机后耳机底噪非常大，需要睡眠重新唤醒后解决

## 致谢

- [the-darkvoid](https://github.com/the-darkvoid/XPS9360-macOS)
- [bozma88's guide](https://www.tonymacx86.com/threads/guide-dell-xps-13-9360-on-macos-sierra-10-12-x-lts-long-term-support-guide.213141/)
- [DalianSky](https://blog.daliansky.net/)