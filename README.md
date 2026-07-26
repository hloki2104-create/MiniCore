# MiniCore

MiniCore 是一个面向轻量化边缘计算平台的开源 SOC 底板仓库。

本仓库用于集中开源我们设计的不同型号 SOC 底板。每一个型号都以独立文件夹维护，根目录 README 负责说明项目定位、仓库结构、型号索引、版本状态、贡献方式和致谢信息；具体型号的硬件资料放在各自目录内。

## 项目目标

MiniCore 系列底板面向无人机、机械臂、移动机器人和其他需要轻量化边缘计算平台的工况，目标是在较小体积内提供可靠供电、清晰接口定义、可复现硬件资料和可读的上手文档。

本仓库重点维护：

- SOC 核心板底板设计资料
- 每个底板型号的 README 和 DATASHEET
- PCB 工程压缩包、Gerber、BOM 或其他制板资料
- 接口定义、供电说明、外设连接说明
- 系统烧录、调试和应用部署参考
- 版本记录、问题修订和资料更新说明


## 版本

| 版本 | 日期 | 说明 |
|------|------|------|
| V0.1 | 2026-7-01 | 建立 MiniCore 开源仓库结构 |
| V0.2 | 2026-7-21 | 整理 MiniCoreV2 文档与附件 |
| V0.3 | 2026-7-26 | 新增 MiniCore-RadxaCm4V1 型号 |


## 仓库结构

```text
MiniCore/
|-- README.md
|-- LICENSE
|-- MiniCoreV2/
|   |-- README.md
|   |-- Loki-MiniCoreV2-basesheet.md
|   |-- attachments/
|   `-- *.zip
|-- MiniCore-RadxaCm4V1/
|   |-- README.md
|   |-- DATASHEET.md
|   |-- attachments/
|   `-- *.zip
`-- MiniCoreV4D/
    |-- README.md
    |-- DATASHEET.md
    |-- attachments/
    `-- *.zip
```

## 型号索引

| 型号 | 核心平台 | 状态 | 资料 |
|------|----------|------|------|
| MiniCoreV2 | RK3588S / CM5 形态 | 已整理 README 与 DATASHEET | [进入 MiniCoreV2](MiniCoreV2/README.md) |
| MiniCore-RadxaCm4V1 | Radxa CM4 | 型号目录已建立，资料补充中 | [进入 MiniCore-RadxaCm4V1](MiniCore-RadxaCm4V1/README.md) |


## 适用方向

- 无人机机载边缘计算平台
- 机械臂控制与感知平台
- 移动机器人主控与扩展平台
- 视觉感知、SLAM、自主规划实验平台
- 国产 SOC 或开源核心板的底板验证与二次开发


## 资料致谢

MiniCore 的整理和验证参考了多个开源社区、芯片平台资料和机器人软件生态。感谢这些公开资料让硬件验证、系统适配和应用部署可以被更多人复现。

特别感谢以下资料与项目提供的基础参考：

- Rockchip RK3588 / RK3588S 相关公开资料与工具生态
- Radxa 等开源硬件社区资料
- ROS、MAVROS、Intel RealSense、VINS、EGO Planner 等开源机器人软件项目
- Livox MID360、Livox SDK2、livox_ros_driver2、FAST-LIO 等感知与 SLAM 相关开源资料

如果仓库文档中引用了第三方项目、图片、工具或链接，其版权和许可归原作者或原项目所有。



## 免责声明

本仓库资料主要用于学习、研究、开发验证和开源硬件交流。硬件设计、供电连接、焊接改线、系统烧录和无人机/机器人调试都可能带来设备损坏或安全风险。请在理解风险的前提下操作，并根据自己的硬件版本进行核对。

仓库中的文档和资料会持续更新，可能存在遗漏、错误或与实际硬件版本不一致的地方。使用前请优先查看对应型号目录中的最新 README、DATASHEET 和版本说明。

## 开源协议

本项目采用 [MIT License](LICENSE) 开源。
