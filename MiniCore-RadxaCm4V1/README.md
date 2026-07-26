# MiniCore-RadxaCm4V1

MiniCore-RadxaCm4V1 是 MiniCore 系列中的 Radxa CM4 型号底板目录。

本目录用于维护该型号底板的 README、DATASHEET、PCB 工程压缩包、图片附件和后续版本记录。当前 README 先作为该型号的资料入口，后续可以继续补充详细接口说明、实物图、原理图、PCBZIP、Gerber、BOM 和调试记录。

## 型号定位

MiniCore-RadxaCm4V1 面向需要使用 Radxa CM4 核心板进行轻量化边缘计算、机器人控制、视觉感知或嵌入式系统验证的场景。

该型号资料建议重点覆盖：

- Radxa CM4 核心板连接与安装说明
- 底板供电方式与电源保护设计
- USB、网口、显示、摄像头和 GPIO 等接口定义
- 外设接线说明
- PCB 工程、Gerber、BOM 和装配资料
- 系统烧录、启动测试和常见问题

## 目录规划

推荐本型号目录后续保持如下结构：

```text
MiniCore-RadxaCm4V1/
├── README.md
├── DATASHEET.md
├── attachments/
│   ├── board-top.jpg
│   ├── board-bottom.jpg
│   └── interface-map.png
├── PCBZIP/
│   └── MiniCore-RadxaCm4V1-PCB.zip
├── Gerber/
│   └── MiniCore-RadxaCm4V1-Gerber.zip
└── BOM/
    └── MiniCore-RadxaCm4V1-BOM.csv
```

## 资料状态

| 资料 | 状态 | 说明 |
|------|------|------|
| README | 已建立 | 当前文件 |
| DATASHEET | 待补充 | 建议记录完整接口、电源、引脚和注意事项 |
| 实物图片 | 待补充 | 建议放入 `attachments/` |
| PCBZIP | 待补充 | 建议放入 `PCBZIP/` |
| Gerber | 待补充 | 建议放入 `Gerber/` |
| BOM | 待补充 | 建议放入 `BOM/` |

## README 建议内容

后续完善该型号时，建议 README 保持快速可读，只放入口级信息：

- 型号简介
- 实物图
- 核心特性
- 接口速览
- 资料下载与文件说明
- 快速上手
- 注意事项
- 版本记录
- 开源协议

详细接口、电源、引脚、测试流程等内容建议放入 `DATASHEET.md`。

## 快速开始

当前该型号详细资料仍待补充。后续建议按以下顺序完善：

1. 上传底板实物图到 `attachments/`。
2. 上传 PCB 工程压缩包或制板资料。
3. 编写 `DATASHEET.md`，补充接口定义、电源说明和注意事项。
4. 在本 README 中补充资料链接和快速上手步骤。
5. 更新根目录 `README.md` 中的型号索引状态。

## 注意事项

- Markdown 图片请使用相对路径，例如 `attachments/board-top.jpg`。
- 不要在文档中写入本机绝对路径。
- PCBZIP、Gerber、BOM 等文件建议使用型号名前缀命名，便于后续多型号维护。

## 版本记录

| 版本 | 日期 | 说明 |
|------|------|------|
| V1.0 | 待补充 | 建立 MiniCore-RadxaCm4V1 型号目录 |

## 开源协议

本型号资料随 MiniCore 仓库采用 [MIT License](../LICENSE) 开源。
