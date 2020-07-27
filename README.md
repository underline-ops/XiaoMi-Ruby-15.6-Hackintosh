# XiaoMi-Ruby-15.6 Hackintosh
XiaoMi-Ruby-15.6 Hackintosh   (support Big Sur bata)

## 配置 Computer configuration

| 规格     | 详细信息                                   							  					|
| -------- | ---------------------------------------------------------					|
| 电脑型号 | 小米笔记本 Ruby 15.6" 2019款 独显款(UHD 620 + MX 110)      				|
| 处理器  | Intel(R) Core(TM) i5-8250U                      							|
| 内存  | SK hynix 16GB DDR4 2400MHz												|
| 硬盘  | KINGSTON MS80000058688  (238 GB)	M.2(SATA)								|
| 集成显卡  | Intel(R) UHD Graphics 620  (1 GB)          					|
| 内置显示器  | 中电熊猫 ID	NCP002A 1920x1080 IPS 15.6"					|
| 外接显示器  | 1920x1080 							        								|
| 声卡     | Realtek ALC256 (M) 											|
| 网卡     | 无线：DW 1820A	有线：Realtek RTL 8168B				                		|
| 触控板   | I2C HID 																	|
| 照相机   | XiaoMi USB 2.0 WebCam 														|
| 读卡器   | Realtek USB 2.0 Card Reader 												|

|Specifications | details|
| -------- | ---------------------------------------------------------					|
|Computer model | Xiaomi notebook Ruby 15.6 "2019 unique model (UHD 620 + MX 110)|
|Processor | Intel (R) core (TM) i5-8250u|
|Memory | SK Hynix 16GB DDR4 2400mhz|
|Hard disk | Kingstone ms80000058688 (238 GB) m.2 (SATA)|
|Integrated graphics card | Intel (R) UHD graphics 620 (1 GB)|
|Built in display | CLP panda ID | ncp002a 1920x1080 IPS 15.6 "|
|External display | 1920x1080|
|Sound card | Realtek alc256 (m)|
|Network card | wireless: DW 1820a; wired: Realtek RTL 8168b|
|Touch panel | I2C hid|
|Camera | Xiaomi USB 2.0 webcam|
|Reader | Realtek USB 2.0 card reader|
## 注意 attention!
在使用Big Sur bata版本升级时请确认此opencore版本是否与之兼容

在实操之前请自行[修改 SMbios 信息](https://github.com/corpnewt/GenSMBIOS) !

可以仿冒HiDPI以获得最佳显示效果

When upgrading with the Big Sur Bata version, please confirm that this OpenCORE version is compatible with it.

You can impersonate hidpi for the best display

## 无法正常工作的硬件 Hardware that doesn't work
1.自带触控板 (等待后续内核更新)
2.内置外放 

1.touch panel (waiting for subsequent kernel update)
2.Internal Speaker (Intel® Smart Sound Technology)

Laptops with Intel SST will not have anything connected through them (usually internal mic) work, as it is not supported. You can check with Device Manager on Windows.
## 以下为XenOriginal的相关教程说明~
## From Clover to Opencore

1. Use scripts unlock CFG and set DVMT

2. Press Space in OpenCore boot page, and then select Clean NVRAM entry

## Features

1. Opencore Bootloader and all Hotpatch ACPI tables

2. Unlock CFG and DVMT limit, more original to mac

3. 99% Hardware is perfect even FN-Backlight button

## Hardware

For a 99% perfect Hackintosh on Xiaomi-Ruby-15.6-UMA-only, you need do following things.

1. Replace Wireless Network Cards from Realtek to BCM94360CS2 - Necessary

2. Replace your monitor from 45% NTSC to 72% NTSC (N156HCE-EN1) - Optional

3. Replace your m2 ssd from SATA to NVME - Optional

4. Upgrade your memory - Optional

5. Buy a good bluetooth soundbar - Optional

## BIOS Setting

1. Set a bios password and disable scurity boot - Necessary

2. Use scripts unlock CFG and set DVMT - Recommend (You can roll back by restore bios setting)

    You can test in Opencore boot page
    
## Generate your own SMbios

  Platforminfo

  For setting up the SMBIOS info, we'll use CorpNewt's GenSMBIOS and ProperTree application. https://github.com/corpnewt/GenSMBIOS https://github.com/corpnewt/ProperTree

  Because of the KabyLake R, we'll choose the MacBookPro14,2 SMBIOS:

  Run GenSMBIOS, pick option 1 for downloading MacSerial and Option 3 for selecting out SMBIOS. This will give us an output similar to the following:

  Type: MacBookPro14,2

  Serial: C02WXAY2HV2N

  Board Serial: C02826303CDHRPC8C

  SmUUID: 88AA1336-8DF9-477A-A39F-03D016ED0809

  The order is Product | Serial | Board Serial (MLB)

  The Type part gets copied to Generic -> SystemProductName.

  The Serial part gets copied to Generic -> SystemSerialNumber.

  The Board Serial part gets copied to Generic -> MLB.

  The SmUUID part gets copied toto Generic -> SystemUUID.

  We set Generic -> ROM to either an Apple ROM (dumped from a real Mac), your NIC MAC address, or any random MAC address (could be just 6 random bytes, for this guide we'll use 11223300 0000. After install follow the Fixing iServices page on how to find your real MAC Address)

  Reminder that you want either an invalid serial or valid serial numbers but those not in use, you want to get a message back like: "Invalid Serial" or "Purchase Date not Validated"

  Apple Check Coverage page https://checkcoverage.apple.com/cn/zh/    

## 作者 author
在[XenOriginal 的 EFI ](https://github.com/XenOriginal/XiaoMi-Ruby-15.6-UMA-only)基础上进行修改,opencore升级到0.6.0-07-23,kext必要更新替换.

In [XenOriginal EFI ](https://github.com/XenOriginal/XiaoMi-Ruby-15.6-UMA-only),opencore is upgraded to 0.6.0-07-23, and kext needs to be updated and replaced
