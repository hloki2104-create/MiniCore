# MiniCoreV2 

本项目致力于为无人机，机械臂等需要轻量化边缘计算平台的工况提供我们的开源解决方案：
依据于RK3588S国产SOC，CM5形态，并为之设计了我们的底板-- MiniCore-V2


![MiniCore-V2 实物图](attachments/IMG_20251229_162550.jpg)
![MiniCore-V2 实物图](attachments/IMG_20260408_001403.jpg)

## 项目概览

MiniCore-V2 是一块围绕 RK3588S CM5 核心板设计的轻量化载板，当前我们已经整理了：

- MiniCore-V2 硬件说明
    - 主要接口定义与供电说明
    - 系统镜像与 Rockchip 烧录工具下载入口
- EMMC 烧录流程
- OV13855 摄像头基础测试流程
- ROS1、MAVROS、RealSense、VINS、EGO Planner 的部署参考

## 适用方向

- 无人机机载边缘计算平台
- 机械臂与移动机器人控制器
- 视觉感知与自主规划实验平台
- 需要国产高性能 SoC 的轻量化嵌入式系统


## 硬件特点

MiniCore-V2 具备接口总览如下：

- 1x USB3.0 Type-C
- 1x 全功能 Type-C OTG
- 4x SH1.0-USB2.0
- 3x SH1.0-UART
- 1x SH1.0-PWM x2
- 1x SH1.0-CAN1
- 1x SH1.0-SPI0
- 1x MIPI-CSI
- 1x MIPI-DSI
- 1x 8PIN 多功能排母
- 1x SH1.0 电源输入
- 1x 用户自定义开关

更详细的引脚定义、复用说明、接线图和实物标注，请查看：

- [Loki-MiniCoreV2-basesheet.md](Loki-MiniCoreV2-basesheet.md)

## 资料导航

### 1. 硬件说明

完整硬件文档位于：

- [Loki-MiniCoreV2-basesheet.md](Loki-MiniCoreV2-basesheet.md)

该文档目前包含：

- 硬件实物图
- 接口总览
- 电源、风扇、网口、USB、UART、PWM、CAN、SPI 详细说明
- 8PIN 多功能排母定义
- MIPI CSI 摄像头说明
- USB HUB 子板说明
- 推荐配件与注意事项
- 系统资源下载
- 刷机与相机测试流程
- 自主规划算法部署参考

### 相关参考资料
- [MID360 Official Website](https://www.livoxtech.com/cn/mid-360)
- [Quick Start Guide for MID360](https://terra-1-g.djicdn.com/65c028cd298f4669a7f0e40e50ba1131/Mid360/Livox_Mid-360_Quick_Start_Guide_multi.pdf)
- [MID360 User Manual](https://terra-1-g.djicdn.com/65c028cd298f4669a7f0e40e50ba1131/Mid360/20230727/Livox_Mid-360_User_Manual_CHS.pdf)
- [Livox SDK2 Source Code](https://github.com/Livox-SDK/Livox-SDK2)
- [Livox ROS Driver 2 Source Code](https://github.com/Livox-SDK/livox_ros_driver2)

- [Livox ROS Driver 2 Installation Guide](https://blog.csdn.net/qq_29912325/article/details/130269367)
- [Virtual Machine and MID360 Bridging Guide](https://blog.csdn.net/sinat_39110395/article/details/123545816)

### Livox and Fast-Lio Configuration Process
1. Install [Livox SDK2](https://github.com/Livox-SDK/Livox-SDK2). The installation steps are detailed in the README. **Note:** Change the host IP to `192.168.1.50`. [How to modify Ubuntu IP](https://blog.csdn.net/sinat_39110395/article/details/123545816). The Lidar IP in this setup is `192.168.1.180`.
2. Install [Livox ROS Driver 2](https://github.com/Livox-SDK/livox_ros_driver2). Follow the steps in the README. **Note:** Before running, make sure to modify the host IP and Lidar IP in the configuration files.
3. Configure Fast-LIO:

References:  
- [FAST_LIO Repository](https://github.com/hku-mars/FAST_LIO)  
- [FAST-LIO Configuration Guide (Chinese)](https://blog.csdn.net/qq_42108414/article/details/131530293)  
- [Using MID360 with FAST-LIO2 on ROS1](https://blog.csdn.net/qq_52784762/article/details/132736322)  


## 配套与扩展

关于本底板，我们还推荐以下配件和相关事项：

- USB HUB 子板三种工作模式说明
- 天线、散热器、电源、DCDC、FPC Type-C 线等推荐配件
- 供电、接线、散热和焊接注意事项

## 使用建议

- 建议使用 5V/5A 或更高规格电源供电
- 使用 Type-C OTG 烧录时，优先按文档说明操作，避免错误供电
- USB HUB 模式与供电模式不要同时使用
- 使用 MIPI 摄像头时，注意 FPC 线方向与 Camera 口选择
- 涉及 GPIO 复用、焊接改线和散热器改线时，建议有硬件经验后再操作
