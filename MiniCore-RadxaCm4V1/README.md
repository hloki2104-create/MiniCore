# MiniCore-RadxaCm4V1

MiniCore-RadxaCm4V1 是 MiniCore 系列中的 Radxa CM4 型号底板目录。



## 型号定位

MiniCore-RadxaCm4V1 面向需要使用 Radxa CM4 核心板进行轻量化边缘计算、机器人控制、视觉感知或嵌入式系统验证的场景。


## Radxa CM4 简介

Radxa CM4 是 Radxa 推出的高性能 System on Module（SoM）计算模块，面向空间受限的嵌入式应用、工业控制、边缘计算、机器视觉和多媒体场景。根据 Radxa 官方资料，Radxa CM4 基于 Rockchip RK3576 / RK3576J，采用 55 mm x 40 mm 紧凑形态，并通过 3 组 100 Pin B2B 连接器向底板引出高速接口和常用外设接口。

![](<attachments/cm4_core_interface.webp>)

| 序号 | 说明 | 序号 | 说明 | 序号 | 说明 | 序号 | 说明 |
|------|------|------|------|------|------|------|------|
| ① | LPDDR4X 内存 | ③ | SoC:Rockchip RK3576(J) | ⑤ | 天线接口 | ⑦ | 板载 eMMC |
| ② | Maskrom 按键 | ④ | SPI Flash | ⑥ | WiFi/BT 芯片 | ⑧ | 3x 100 Pin B2B 连接器 |


核心能力包括：

- CPU：4 核 Cortex-A72 + 4 核 Cortex-A53，最高 2.2 GHz
- GPU：Arm Mali G52 MC3
- NPU：最高 6 TOPS INT8 AI 算力
- 内存：LPDDR4X，最高 16 GB
- 存储：板载 eMMC，最高 128 GB，并支持 SDMMC 等启动或数据存储方式
- 网络：千兆以太网，可选 Wi-Fi 6 / Bluetooth 5.4
- 多媒体：支持 HDMI、eDP、DP、MIPI DSI、MIPI CSI 等显示与摄像头接口
- 系统：支持 Debian Linux、Android、Buildroot、Yocto 等系统

MiniCore-RadxaCm4V1 底板围绕 Radxa CM4 的 B2B 扩展能力展开，目标是把核心板能力以更适合机器人和边缘计算验证的形式引出，并为后续供电、接口、外设连接和 PCB 资料提供开源文档入口。

参考资料：

- [Radxa CM4 产品页](https://radxa.com/products/cm/cm4/)
- [Radxa CM4 官方文档](https://docs.radxa.com/en/som/cm/cm4)
- [Radxa CM4 硬件信息](https://docs.radxa.com/en/som/cm/cm4/hardware-use/hardware_info)


## README 内容

- PCB 文件：[MiniCore-RadxaCm4_V1.1.epro](MiniCore-RadxaCm4_V1.1.epro)


- 型号简介
- 实物图
![](<attachments/屏幕截图 2026-07-26 224418.png>)
- 核心特性
- 接口速览
- 资料下载与文件说明
- 快速上手
- 注意事项
- 版本记录
- 开源协议


## 版本记录

| 版本 | 日期 | 说明 |
|------|------|------|
| V1.0 | 2026-7-26 | 建立 MiniCore-RadxaCm4V1 型号目录 |

## 开源协议

本型号资料随 MiniCore 仓库采用 [MIT License](../LICENSE) 开源。
