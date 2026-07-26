# MiniCore

MiniCore 是一个面向轻量化边缘计算平台的开源 SOC 底板仓库。

本仓库用于集中开源我们设计的不同型号 SOC 底板。每一个型号都会以独立文件夹的形式维护，例如 `MiniCoreV2`、`MiniCore-RadxaCm4V1`、后续的 `MiniCoreV4D` 等。根目录 README 负责说明项目定位、仓库结构和型号索引；各型号文件夹内的 README、DATASHEET、PCBZIP 等资料负责描述具体硬件。

## 项目目标

MiniCore 系列底板面向无人机、机械臂、移动机器人和其他需要轻量化边缘计算平台的工况，目标是在较小体积内提供可靠供电、清晰接口定义、可复现硬件资料和可读的上手文档。

当前仓库重点覆盖以下内容：

- SOC 核心板底板设计资料
- 每个底板型号的 README 与 DATASHEET
- PCB 工程压缩包或制板资料
- 接口定义、供电说明、外设连接说明
- 系统烧录、调试和应用部署参考

## 仓库结构

推荐的仓库结构如下：

```text
MiniCore/
├── README.md
├── LICENSE
├── MiniCoreV2/
│   ├── README.md
│   ├── Loki-MiniCoreV2-basesheet.md
│   ├── attachments/
│   └── *.zip
├── MiniCore-RadxaCm4V1/
│   ├── README.md
│   ├── DATASHEET.md
│   ├── attachments/
│   └── *.zip
└── MiniCoreV4D/
    ├── README.md
    ├── DATASHEET.md
    ├── attachments/
    └── *.zip
```

其中：

- `README.md`：仓库总说明，只做系列介绍、型号导航和贡献规范。
- `型号文件夹/README.md`：该型号底板的入口文档，说明用途、硬件特点、资料列表和快速开始。
- `型号文件夹/DATASHEET.md`：该型号底板的详细资料文档，包含接口、电源、引脚、注意事项等。
- `型号文件夹/attachments/`：该型号 README 和 DATASHEET 使用的图片文件。
- `型号文件夹/*.zip`：该型号 PCB 工程、Gerber、BOM 或其他硬件资料压缩包。

## 型号索引

| 型号 | 核心平台 | 状态 | 资料 |
|------|----------|------|------|
| MiniCoreV2 | RK3588S / CM5 形态 | 已整理 README 与 DATASHEET | [进入 MiniCoreV2](MiniCoreV2/README.md) |
| MiniCore-RadxaCm4V1 | Radxa CM4 | README 已建立，资料待补充 | [进入 MiniCore-RadxaCm4V1](MiniCore-RadxaCm4V1/README.md) |

## 文档规范

为了让仓库后续扩展更多底板型号时仍然清晰，建议每个型号文件夹保持一致的组织方式：

1. `README.md` 放在型号文件夹第一层，作为该型号的快速入口。
2. 详细硬件说明单独放在 `DATASHEET.md` 或明确命名的 datasheet 文档中。
3. README 和 DATASHEET 中的图片统一放入本型号的 `attachments/` 文件夹。
4. Markdown 中使用相对路径，例如 `attachments/board-top.jpg`。
5. 不在 Markdown 中使用本机绝对路径。
6. PCB 工程、Gerber、BOM、装配资料等以清晰文件名放入型号文件夹。

## 适用方向

- 无人机机载边缘计算平台
- 机械臂控制与感知平台
- 移动机器人主控与扩展平台
- 视觉感知、SLAM、自主规划实验平台
- 国产 SOC 或开源核心板的底板验证与二次开发

## 开源协议

本项目采用 [MIT License](LICENSE) 开源。

## 维护说明

如果你要提交某一个型号的新版本，建议只提交该型号文件夹，例如：

```powershell
git add MiniCoreV2
git commit -m "docs: update MiniCoreV2"
git push upstream HEAD:main
```

如果是新增型号，例如 `MiniCore-RadxaCm4V1`，则提交该型号文件夹和根目录索引：

```powershell
git add README.md MiniCore-RadxaCm4V1
git commit -m "docs: add MiniCore-RadxaCm4V1"
git push upstream HEAD:main
```
