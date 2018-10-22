# XPS 9360 hackintosh
目前在Mojave下正常使用

# 硬件配置
- Intel i7 8550u
- 16G RAM
- 闪迪A400 512G NVME SSD
- 夏普 SHP144A (LQ133Z1) 分辨率3200*1800
- 内置的无线网卡为killer 1535，更换为某宝上的拆机DW1560
- 声卡ALC256

# 注意事项
- 安装使用了[DalianSky](https://blog.daliansky.net/)的镜像，安装过程中会多次报错，强制重启后能顺利进入下一阶段。
- 按照the-darkvoid的说明，事先将BIOS和雷电固件都升级到最新
- 已在the-darkvoid的基础上打上了minStolenSize补丁。[详见](https://blog.daliansky.net/Common-problems-and-solutions-in-macOS-Mojave-10.14-installation.html#minStolenSize%E6%96%B0%E8%A1%A5%E4%B8%81%EF%BC%8C%E7%94%A8%E4%BA%8EBroadwell-Skylake-%E4%BB%A5%E5%8F%8AKabylake)
- 注意BIOS设置。硬盘模式选择AHCI，关闭启动相关的安全选项，开启雷电接口的相关选项；根据需要关闭触摸屏等功能；
- Mojave下的声卡需要用AppleALC注入layout_id=11，[详见](https://github.com/the-darkvoid/XPS9360-macOS/issues/85)
其他方式可能会导致诸如声卡无法驱动、能驱动但是导致kernel_task占用大量CPU资源等异常情况(都是泪)
- 其他待补充

# 问题
- 目前碰到的问题是Anywhere2 通过蓝牙连接使用会时不时的突然无法使用，断开重连后正常，不知道原因

## 致谢

- [the-darkvoid](https://github.com/the-darkvoid/XPS9360-macOS)
- [DalianSky](https://blog.daliansky.net/)