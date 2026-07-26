
![](<attachments/IMG_20251229_162550.jpg>)
![](<attachments/IMG_20260408_001403.jpg>)
![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Image_1771601828382_589 1.jpg](<attachments/Image_1771601828382_589 1.jpg>)

![](<attachments/IMG_20251228_143226.jpg>)

# 硬件说明
## OrangeCM5芯片框图
本底板专为RK3588CM5核心板设计
- RK3588S2
- RK3588S1
![rock 5c overview](https://docs.radxa.com/img/rock5c/rk3588s2_blockdiagram.webp)

## 实物
![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Image_1784983344614_976 1.jpg](<attachments/Image_1784983344614_976 1.jpg>)
![](<attachments/IMG_20251228_143226.jpg>)
## 接口总览

![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260601222127 1.png](<attachments/Pasted image 20260601222127 1.png>)
- 1x USB3.0 (注意 **仅單面** Type-C)
- 1x 全功能 Type-C OTG
- 4x SH1.0-USB2.0
- 3x SH1.0-UART (可當 GPIO*2)
- 1x SH1.0-PWM*2 (可當 GPIO*2)
- 1x SH1.0-CAN1 (可當 GPIO*2)
- 1x SH1.0-SPI0 (可當 GPIO*2)
- 1x MIPI-CSI
- 1x MIPI-DSI
- 1x 8PIN 多功能排母 (GPIO4，可當兩組 UART/IIC 或一組 SPI，及一組 USB2)
- 1x SH1.0 電源輸入
- 1x 用戶自定義開關 GPIO4_A6


## 接口详情

### 电源接口

- **SH1.0 电源输入**：5V 输入，带防反接二极管
- **Type-C OTG & PD 输入**：支持烧录系统，**建议使用 5V/4A~6A 电源适配器**

**供电说明**：
![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725164409 1.png](<attachments/Pasted image 20260725164409 1.png>)
- 上图中红圈的 SH1.0 接口（从上到下为 ++--），输入电压 5V，带防反接二极管

![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725164421 1.png](<attachments/Pasted image 20260725164421 1.png>)
- 红圈中的开关在 **NO** 状态时，可使用 Type-C OTG 供电（**请仅在烧录时使用**）

### PWM风扇接口

![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725164026 1.png](<attachments/Pasted image 20260725164026 1.png>)
PWM 由 5V,GPIO1_A7(PWM3-M3, GPIO1-C6(PWM15-M2,GND 組成

### 有线网口（百兆）

![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725164036 1.png](<attachments/Pasted image 20260725164036 1.png>)
提供百兆以太网接口。
![硬件栈/SOC/RK/rk3588/ROS栈/attachments/qq_pic_merged_1784983637351 1.jpg](<attachments/qq_pic_merged_1784983637351 1.jpg>)

| Pin | Name      | Pin | Name      |
| --- | --------- | --- | --------- |
| 1   | ETH0_D+   | 2   | ETH0_D-   |
| 3   | ETH1_D+   | 4   | ETH1_D-   |

对应 RJ45 的 1、2、3、6 引脚。

接线图：
![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Image_1784983013643_394 1.jpg](<attachments/Image_1784983013643_394 1.jpg>)
### SH1.0-USB2.0 接口
![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725164051 1.png](<attachments/Pasted image 20260725164051 1.png>)

| 引脚 | 信号 |
|------|------|
| 1 | 5V |
| 2 | D- |
| 3 | D+ |
| 4 | GND |

### SH1.0-UART 接口（可当 GPIO×2）
![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725205805 1.png](<attachments/Pasted image 20260725205805 1.png>)
所有 UART 接口引脚排列（从左到右）：`5V` `(Rx)` `(Tx)` `GND`

| 接口 | Rx 引脚 | Tx 引脚 |
|------|---------|---------|
| UART1-M1 | GPIO1_B7 | GPIO1_B6 |
| UART2-M1 | GPIO4_D1 | GPIO4_D0 |
| UART4-M2 | GPIO1_B2 | GPIO1_B3 |
| UART6-M1 | GPIO1_A0 | GPIO1_A1 |

### SH1.0-PWM 接口（可当 GPIO×2）

引脚排列（从左到右）：`5V` `PWM1` `PWM2` `GND`

| 接口 | 引脚 | 功能 |
|------|------|------|
| PWM3-M3 | GPIO1_A7 | PWM 输出 |
| PWM15-M2 | GPIO1_C6 | PWM 输出 |

### SH1.0-CAN 接口（可当 GPIO×2）

引脚排列（从左到右）：`5V` `CAN_Rx` `CAN_Tx` `GND`

| 接口 | Rx 引脚 | Tx 引脚 |
|------|---------|---------|
| CAN1-M1 | GPIO4_B2 | GPIO4_B3 |

### SH1.0-SPI 接口（可当 GPIO×2）

**SPI0-M2 引脚分配**：

| 信号 | 引脚（左图） | 信号 | 引脚（右图） |
|------|-------------|------|-------------|
| MOSI | GPIO1_B2 | CS0 | GPIO1_B4 |
| CLK  | GPIO1_B3 | MISO | GPIO1_B1 |
| 5V   | -          | GND  | -           |

### 8PIN 多功能排母
![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725163951 1.png](<attachments/Pasted image 20260725163951 1.png>)
手拿排母从左到右引脚定义：

| 引脚 | 信号 |
|------|------|
| 1 | GPIO1-D0 |
| 2 | GPIO1-D1 |
| 3 | GPIO1-D2 |
| 4 | GPIO1-D3 |
| 5 | USB_N |
| 6 | USB_P |
| 7 | GND |
| 8 | 5V |

#### 功能复用配置

| 功能 | 引脚映射 |
|------|----------|
| UART6-M2 | Rx=GPIO1-D1, Tx=GPIO1-D0 |
| IIC7-M0 | SDA=GPIO1-D1, SCL=GPIO1-D0 |
| UART4-M0 | Rx=GPIO1-D3, Tx=GPIO1-D2 |
| IIC1-M4 | SDA=GPIO1-D3, SCL=GPIO1-D2 |
| SPI1-M2 | MISO=GPIO1-D0, MOSI=GPIO1-D1, CLK=GPIO1-D2, CS0=GPIO1-D3 |

#### GPIO 电压规格

| GPIO 类型 | 电压 | 最高耐压 |
|-----------|------|----------|
| 所有 GPIO | 3.3V | 3.63V |

### MICRO HDMI

配备mICRO HDMI 接口
![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725225953 1.png](<attachments/Pasted image 20260725225953 1.png>)
**特性**：HDMI 接口接入了 EEPROM，可以不插诱骗器在 NoMachine 远程使用。香橙派 CM5/5B 的系统不需要诱骗器即可远程。

### USB 接口
![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725205519 1.png](<attachments/Pasted image 20260725205519 1.png>)

**⚠️ 注意！！！USB3.0接口为单面！！识别不到或者无法满足要求可以尝试更换反面！！！**

![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725205655 1.png](<attachments/Pasted image 20260725205655 1.png>)
![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725205700 1.png](<attachments/Pasted image 20260725205700 1.png>)

| 接口类型 | 数量 | 说明 |
|----------|------|------|
| USB3.0 Type-C | 1 | 单面 |
| 全功能 Type-C OTG | 1 | 可用于烧录系统（按住 BOOT 再上电） |
| SH1.0-USB2.0 | 4 | 5V/D-/D+/GND |


### MIPI CSI

![](<attachments/IMG_20260725_202349.jpg>)
支持 MIPI 摄像头, 采用了 31PIN 0.3mm 脚距 FH35C-31S-0.3SHW(50) 镀金座子。

参考[1300万像素摄像头（13855）](http://www.orangepi.cn/html/hardWare/computerAndMicrocontrollers/details/13-MP-Camera-13855.html)
![硬件栈/SOC/RK/rk3588/ROS栈/attachments/qq_pic_merged_1784983525640 1 1.jpg](<attachments/qq_pic_merged_1784983525640 1 1.jpg>)

目前开发板支持两款MIPI摄像头，OV13850 和OV13855
具体的图片如下所示：
![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725205144 1.png](<attachments/Pasted image 20260725205144 1.png>)
a. 1300 万MIPI接口的OV13850 摄像头

![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725205150 1.png](<attachments/Pasted image 20260725205150 1.png>)
b. 1300 万MIPI接口的OV13855 摄像头。

OV13850 和OV13855 摄像头使用的转接板和FPC排线是一样的，只是两款摄像
头接在转接板上的位置不一样。
FPC排线如下图所示，
![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725205208 1.png](<attachments/Pasted image 20260725205208 1.png>)
请注意FPC排线是有方向的，
标注TO MB那端需要插到开发板的摄像头接口中，标注TO CAMERA那端需要插到
摄像头转接板上。
系统中只有 CAM1 可以用来接 OV13850 或 OV13855 摄像头。



### 用户自定义开关

- **GPIO4_A6**：用户自定义按键

---

### USB HUB 子板说明
![](<attachments/IMG_20260725_202438.jpg>)
#### 工作模式

| 模式 | 说明 |
|------|------|
| **模式一：独立 USB HUB** | Type-C 接口作为 USB HUB 输入，可连接电脑使用，也可接入 5V/4A 适配器供电 |
| **模式二：CM5 供电器** | Type-C 接入 5V/4A 适配器，右侧 SH1.0 口输出电源给 CM5 供电（此时 USB HUB 功能不可用） |
| **模式三：CM5 USB HUB** | 将 USBIN 的 SH1.0 接入 CM5 的 SH1.0 USB 接口，作为 CM5 的 USB HUB 使用 |

#### USB HUB 接口分配
![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725201619 1.png](<attachments/Pasted image 20260725201619 1.png>)
- 2 × USB-A
- 2 × SH1.0 USB（电源输出为 3.3V）

> **⚠️ 注意**：供电模式和 USB HUB 模式不能同时工作！

---

## 🛒 推荐配件

### 1. 天线
- 型号：FPC 25×9mm，IPEX 4代接口
- 链接：[点击查看](https://e.tb.cn/h.hokmrR7hdwkJPQp?tk=bnwb4TbYVtf)

### 2. 散热器
![](<attachments/Screenshot_2026-07-25-21-03-13-344_com.taobao.ta.jpg>)
- **需要改线路**：将原线序改为：黑 → 黄 → 蓝 → 红
- 链接：[点击查看](https://e.tb.cn/h.hr61t6j4rWMbQmj?tk=Tc7C4iwU7TM)

### 3. 电源适配器
- 规格：5V/5A
- 链接：[点击查看](https://e.tb.cn/h.hLXRHAoSP7hww9J?tk=DwtO4Tb3Y0S)

### 4. 5V DCDC 模块
- 链接：[点击查看](https://e.tb.cn/h.hoktLvvIXoDKxrg?tk=yvd44Tb5gnL)

### 5. FPC Type-C 线
- 规格：**无芯片**版本
- 链接：[点击查看](https://e.tb.cn/h.hI1fzRUwbJa73Sp?tk=eQ164RPfhXx)

## ⚠️ 注意事项

1. **供电要求**：建议使用 5V/5A 或更高规格的电源
2. **防反接**：SH1.0 电源输入已带防反接二极管，但 Type-C 输入无保护
3. **USB HUB 模式**：供电模式和 USB HUB 模式不能同时使用
4. **散热器改装**：购买散热器后请按说明改线序
5. **焊接操作**：如需修改 40-Pin USB 功能配置，建议由有经验的技术人员完成

# 资源下载汇总


## 操作系统镜像

### 提供简单适配的操作系统镜像

**MiniCoreV2系统**
-    Ubuntu20.04
	装好ros1,realsense,vins ego(没做调试)
	```
	用戶名:orangepi 密碼(小寫L):l
	```
	https://pan.baidu.com/s/1dXIxiatij07BU-YQQDy7Aw?pwd=rgex

**loki的ubuntu20系统**
-    Ubuntu20.04(纯系统无软件，刷机或其他使用)
	
	
	用戶名:orangepi 密碼(小寫L):l
	
	https://pan.baidu.com/s/1_ds5qjKl700lFKau_oatoA?pwd=ngis

**警告**
除了上面的镜像经过测试可以使用外，其他厂家镜像未经过测试，可能会存在未知问题，仅用于评估使用。

**备注**
目前MiniCoreV2提供的Linux 镜像仅为 ROS1可以使用的Ubuntu20.04 版本，其他  版本暂不提供


## RK系统工具
 - RK官方的EMMC燒錄工具
	 **RKDevTool_v3.15:**
	
	https://pan.baidu.com/s/15GJD84DV1e0mozEdzKbzkQ?pwd=j1d6


# 快速上手 
## 1. 安装系统到 EMMC卡

### 1. Type-C OTG 烧录

按住 **BOOT / MaskROM** 按键再上电，即可进入烧录模式进行系统烧录。

### 2. 下載EMMC燒錄工具RKDevTool_v3.15

- 下载解压后，选择DriverAssitant_v5.12文件夹的Driverinstall文件

![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725211640 1.png](<attachments/Pasted image 20260725211640 1.png>)
![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725211647 1.png](<attachments/Pasted image 20260725211647 1.png>)

- 点击启动，跟随指引完成工具下载

![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725211924 1.png](<attachments/Pasted image 20260725211924 1.png>)

###  3. 系统固件下载
- 连接进入BOOT模式的主机，启动程序
- ![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725223908 1.png](<attachments/Pasted image 20260725223908 1.png>)

- 点击浏览键，选择网盘下载好的固件

![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725222746 1.png](<attachments/Pasted image 20260725222746 1.png>)
 
 - 选择EMMC下载

![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725224009 1.png](<attachments/Pasted image 20260725224009 1.png>)

- 强制地址刷写
![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725224129 1.png](<attachments/Pasted image 20260725224129 1.png>)

- **断电重启后即可进入系统**


## 2.OV13855摄像头的简单测试
![硬件栈/SOC/RK/rk3588/ROS栈/attachments/qq_pic_merged_1784983525640 2 1.jpg](<attachments/qq_pic_merged_1784983525640 2 1.jpg>)
###  设备树配置

- 打开终端，运行**orangepi-config**命令，普通用户记得加**sudo**权限
```
sudo orangepi-config
```

-  通过 [设备树配置] 来启用 CM5 Camera1 的 Overlay

	 选择System
![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725231655 1.png](<attachments/Pasted image 20260725231655 1.png>)
	选择Hardware
![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725231705 1.png](<attachments/Pasted image 20260725231705 1.png>)
	下滑选择  **opicm5-tablet-cam1**
![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725231721 1.png](<attachments/Pasted image 20260725231721 1.png>)

![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725231747 1.png](<attachments/Pasted image 20260725231747 1.png>)

 ### 重启系统

- 进入终端 依次测试两条脚本命令，一条失败尝试另一条

```
test_camera.sh
```
```
bash test_camera.sh
```

![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725231909 1.png](<attachments/Pasted image 20260725231909 1.png>)

- 按下 **CTRL+C** 结束命令

![硬件栈/SOC/RK/rk3588/ROS栈/attachments/Pasted image 20260725231920 1.png](<attachments/Pasted image 20260725231920 1.png>)


## 3.自主规划算法部署

### 1-PUTTY连接

![硬件栈/SOC/RK/rk3588/attachments/Pasted image 20260414111718 2.png](<attachments/Pasted image 20260414111718 2.png>)


- 输入3588网卡的ip地址，或者域名（该域名要解析到服务器）
- 指定端口，默认是 22端口。(这个端口要和服务器上的配置一致，默认就是 22 端口)
- 选择连接的协议。(SSH或者串口)
- 点击 open 。

### 2-登录CM5

![硬件栈/SOC/RK/rk3588/attachments/Pasted image 20260414111850 2.png](<attachments/Pasted image 20260414111850 2.png>)

ubuntu20.04 系统
- 用戶名:orangepi 
- 密碼(小寫 L):l 
https://pan.baidu.com/s/1_ds5qjKl700lFKau_oatoA?pwd=ngis 



### 3-ROS安装

	鱼香ROS一键安装命令：
- **wget http://fishros.com/install -O fishros && . fishros 

输入后：

![硬件栈/SOC/RK/rk3588/attachments/Pasted image 20260414112601 2.png](<attachments/Pasted image 20260414112601 2.png>)

![硬件栈/SOC/RK/rk3588/attachments/Pasted image 20260414112706 2.png](<attachments/Pasted image 20260414112706 2.png>)

	一键安装ROS
- **** 输入：1


![硬件栈/SOC/RK/rk3588/attachments/Pasted image 20260414112823 2.png](<attachments/Pasted image 20260414112823 2.png>)

	更换系统源安装
- **** 输入：1

![硬件栈/SOC/RK/rk3588/attachments/Pasted image 20260414113051 2.png](<attachments/Pasted image 20260414113051 2.png>)

	仅更换系统源
- **** 输入：1

![硬件栈/SOC/RK/rk3588/attachments/Pasted image 20260414113539 2.png](<attachments/Pasted image 20260414113539 2.png>)

	选择ROS源
- **** 输入：1

![硬件栈/SOC/RK/rk3588/attachments/Pasted image 20260414113657 2.png](<attachments/Pasted image 20260414113657 2.png>)

	选择ROS1桌面版
- **** 输入：1/1


![硬件栈/SOC/RK/rk3588/attachments/Pasted image 20260414115323 2.png](<attachments/Pasted image 20260414115323 2.png>)

	 安装成功



### 4-MAVROS 与 RealSense 驱动安装

#### 1. MAVROS 安装与配置

`sudo apt install -y ros-noetic-mavros` 
从 ROS 官方仓库安装 MAVROS 核心包。`-y` 表示自动确认，无需手动点击 [Y]。

`cd /opt/ros/noetic/lib/mavros` 
进入系统 MAVROS 的库脚本目录。

`sudo ./install_geographiclib_datasets.sh` 
运行地理数据集下载脚本。这是 MAVROS 正常运行（尤其是处理 GPS 和全球坐标）所必须的数据支撑。

`sudo sed -i '5c <arg name="fcu_url" default="/dev/ttyACM0:921600" />' /opt/ros/noetic/share/mavros/launch/px4.launch`
使用 `sed` 命令直接修改 MAVROS 的启动配置文件。将第 5 行替换为指定的串口设备（`/dev/ttyACM0`）和波特率（`921600`），这是连接 PX4 飞控的硬件通路。

---

#### 2. RealSense 驱动（LibRealSense）安装

`cd ~` 返回用户家目录。

`wget https://github.com/IntelRealSense/librealsense/raw/master/scripts/libuvc_installation.sh` 
从 GitHub 下载 Intel 官方提供的基于 `libuvc` 的安装脚本，这种方式在 Arm 开发板上通常更稳定。

`chmod +x ./libuvc_installation.sh`
给下载的脚本赋予“可执行”权限，使其可以作为程序运行。

`sed -i '12c ##'` libuvc_installation.sh`使用`sed` 修改脚本第 12 行。
通常是为了屏蔽掉脚本中某些不兼容的系统检查或特定的环境变量设置。

`sed -i '47c make -j8' libuvc_installation.sh` 
修改脚本第 47 行，将编译命令改为多线程编译（`make -j8`），以充分利用 Orange Pi CM5 的 8 核 CPU 性能，加快安装速度。

`./libuvc_installation.sh` 
正式执行修改后的安装脚本，开始下载、编译并安装 RealSense 的底层驱动库。

！！！测试用：
`#realsense-viewer` 
这是注释掉的命令，用于在安装完成后通过图形界面检查摄像头是否正常工作。


### 5-vins ego 部署


添加用户到 dialout 组（串口权限） 
```
sudo usermod -a -G dialout $USER 
```
 
#### 1. 代码获取与初始化

![硬件栈/SOC/RK/rk3588/attachments/Pasted image 20260414121711 2.png](<attachments/Pasted image 20260414121711 2.png>)
```
`git clone https://github.com/ZJU-FAST-Lab/Fast-Drone-250` 
```
从 GitHub 远程仓库克隆 Fast-Drone-250 项目的源代码到本地。

![硬件栈/SOC/RK/rk3588/attachments/Pasted image 20260414121724 2.png](<attachments/Pasted image 20260414121724 2.png>)
`cd Fast-Drone-250` 
进入克隆好的项目根目录。

![硬件栈/SOC/RK/rk3588/attachments/Pasted image 20260414121803 2.png](<attachments/Pasted image 20260414121803 2.png>)
`unzip 3rd_party.zip` 
解压项目内置的第三方库压缩包（通常包含 glog、Ceres 等依赖源码）。

![硬件栈/SOC/RK/rk3588/attachments/Pasted image 20260414122157 2.png](<attachments/Pasted image 20260414122157 2.png>)
`sudo chmod 777 -R ~/Fast-Drone-250` 
递归地给项目文件夹赋予最高读写执行权限，防止编译或运行时因权限不足报错。

---

#### 2. 编译安装 glog (Google 日志库)

`cd glog` 
进入解压出的 glog 源码目录。

`./autogen.sh && ./configure && make && sudo make install` 
顺序执行：生成配置脚本、检查环境生成 Makefile、编译代码、最后安装到系统目录。

---

#### 3. 安装系统级数学与 ROS 依赖

`sudo apt install -y liblapack-dev libsuitesparse-dev libcxsparse3 libgflags-dev libgoogle-glog-dev libgtest-dev` 
使用 apt 批量安装线性代数运算（LAPACK）、稀疏矩阵运算以及 gflags 等核心数学开发库。

![硬件栈/SOC/RK/rk3588/attachments/Pasted image 20260414142204 2.png](<attachments/Pasted image 20260414142204 2.png>)
`sudo apt-get install ros-noetic-ddynamic-reconfigure` 
安装 ROS Noetic 版本的动态参数配置插件，用于在不重启节点的情况下调整参数。

---

#### 4. 编译安装 Ceres Solver (非线性优化库)

![硬件栈/SOC/RK/rk3588/attachments/Pasted image 20260414142217 2.png](<attachments/Pasted image 20260414142217 2.png>)
![硬件栈/SOC/RK/rk3588/attachments/Pasted image 20260414143708 2.png](<attachments/Pasted image 20260414143708 2.png>)


`cd ../ceres-solver-2.0.0rc1` 
返回上级并进入 Ceres 优化库的源码目录。

`mkdir build` 
创建编译专用的 build 文件夹，保持源码目录整洁。

`cd build`
进入编译文件夹。

`cmake ..` 
调用 CMake 根据父目录的配置生成当前平台的 Makefile 编译文件。

`sudo make -j8` 
调用 8 个线程并行编译（RK3588 建议使用此倍数），极大缩短编译时间。

`sudo make install` 
将编译生成的库文件安装到系统中，供后续无人机算法调用。

---

#### 5. ROS 工作空间编译与环境配置

![硬件栈/SOC/RK/rk3588/attachments/Pasted image 20260414144624 2.png](<attachments/Pasted image 20260414144624 2.png>)

`cd ../..` 
返回到 Fast-Drone-250 的项目根目录。

`catkin_make` 
调用 ROS 标准编译工具，编译整个 `src` 目录下的所有功能包（如 VINS、EGO-Planner）。

`echo "source ~/Fast-Drone-250/devel/setup.bash" >> ~/.bashrc` 
将当前工作空间的环境变量路径永久添加到用户配置文件的末尾。

`source ~/.bashrc` 
立即刷新当前终端的环境变量，使刚才添加的路径生效。

---


#### 6. 数据存储准备

`mkdir vins_output` 
创建用于存放 VINS 算法实时输出结果的文件夹。

`mkdir -p savedfiles/output/pose_graph` 
递归创建位姿图（Pose Graph）的保存路径，用于后续的地图回放或优化。

---

#### 7. 硬件访问权限与启动脚本

👉 可以直接复制执行
```bash

cd ~  
source ~/Fast-Drone-250/devel/setup.bash  
  
# 1️⃣ RealSense（必须开 IMU，否则 VINS 会卡）  
roslaunch realsense2_camera rs_camera.launch \  
enable_gyro:=true enable_accel:=true unite_imu_method:=linear_interpolation \  
> /tmp/realsense.log 2>&1 & sleep 5  
  
# 2️⃣ MAVROS（连接 PX4）  
roslaunch mavros px4.launch \  
> /tmp/mavros.log 2>&1 & sleep 5  
  
# 3️⃣ VINS（视觉里程计）  
roslaunch vins fast_drone_250.launch \  
> /tmp/vins.log 2>&1 & sleep 5  
  
# 4️⃣ EGO Planner（轨迹规划）  
roslaunch ego_planner single_run_in_exp.launch \  
> /tmp/ego.log 2>&1 & sleep 3  
  
# 5️⃣ MAVROS 指令（调频）  
rosrun mavros mavcmd long 511 105 5000 0 0 0 0 0  
rosrun mavros mavcmd long 511 31 5000 0 0 0 0 0  
  
# 6️⃣ RViz（前台运行）  
roslaunch ego_planner rviz.launch

```
---

`sudo usermod -a -G dialout $USER` 
将当前用户加入 `dialout` 用户组，从而获得直接读写串口（连接 PX4 飞控）的权限。

`roslaunch realsense2_camera rs_camera.launch & sleep 5;` 
后台启动 Intel RealSense 摄像头驱动，并等待 5 秒确认硬件启动成功。

`roslaunch mavros px4.launch & sleep 5;` 
后台启动 MAVROS 节点（建立与 PX4 飞控的通信），并等待 5 秒。

`roslaunch vins fast_drone_250.launch & sleep 3;
后台启动 VINS 视觉里程计，进行状态估计，等待 3 秒。

`roslaunch ego_planner single_run_in_exp.launch & sleep 2;`
后台启动 EGO-Planner 轨迹规划算法，等待 2 秒。

`rosrun mavros mavcmd long 511 105 5000 0 0 0 0 0` 
通过 MAVROS 发送长命令，调整飞控的消息频率（这里通常是请求高频的里程计反馈）。

`rosrun mavros mavcmd long 511 31 5000 0 0 0 0 0`
同上，请求飞控发送特定的姿态或状态数据。

`roslaunch ego_planner rviz.launch` 
启动 RVIZ 可视化界面，观察无人机的飞行路径、地图及状态。

`wait;` 
等待所有后台运行的进程结束（防止主脚本退出导致所有后台节点关闭）。

---

#### 8. 自动化参数修改 (文件配置)

`sudo sed -i '16c output_path: "~/Fast-Drone-250/vins_output"' ~/Fast-Drone-250/src/realflight_modules/VINSFusion/config/fast_drone_250.yaml`
使用 sed 命令直接修改配置文件第 16 行，指定 VINS 的输出路径。

`sudo sed -i '78c pose_graph_save_path: "~/Fast-Drone250/savedfiles/output/pose_graph/"' ~/Fast-Drone250/src/realflight_modules/VINS-Fusion/config/fast_drone_250.yaml` 
修改配置文件第 78 行，指定位姿图数据的保存路径。
 
仿真调用 
`roslaunch ego_planner single_run_in_sim.launch 































