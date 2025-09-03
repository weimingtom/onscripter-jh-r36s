# onscripter-jh-r36s
[WIP] My ONScripter-jh R36S-V5/R36H and RGB10X and Game Kiddy Bubble and RGB10MAX3 port, and for RGB10 with ArkOS.      
Not very good port for RK2020 with ArkOS (factory firmware stock OS is EmuElec not ArkOS), but can be used.    

## Original ONScripter-Jh readme
```
ONScripter是一个开源的NScripter脚本解释工具，主要由Ogapee开发维护
原版的Readme请查看Readme.old。

这是一个修改版的ONScripter源码，在GPLv2协议下发布，使用时请遵守。

修改目标：
	提供比原版ONScripter更好的性能，适当增加一些功能
	添加中文支持
	尽可能的兼容原版ONS脚本
	
进度

	SDL2分支提供各种改进并可在SDL2环境编译
	目前Windows、Android、iOS、Linux、Windows Phone平台均编译通过实测可用，其余平台未测试
```

## [WIP] How to Build  
* Modify Makefile, where are gcc and stage_files   
* Run 'make clean && make MIYOO=1'  

## Cross compile gcc toolchain and SDK stage files    
* aarch64-buildroot-linux-gnu_sdk-buildroot.tar.gz  
from rg351p-toolchain,  
https://github.com/AdrienLombard/sm64-351elec-port/releases/tag/v1.0.0  

## TODO and bugs   
* Check key map  

## R36S and R36H (ArkOS for RG351MP) and RGB10X (ArkOS mod) eth0 ssh user/pass    
* ark/ark  
```
我似乎拿到R36S掌机的控制台，前提是需要准备一个USB转网线的转接器，方法是：
（1）用网线转接器接网线连到路由上，u口接右边的OTG口
（2）通过掌机查询ip和打开远程服务，参考dov/r36s-programming，
虽然这个开源项目说的是无线网卡，但也适用于USB网线转接器
（3）然后用查询到的ip通过putty或者winscp之类的工具登录到控制台，
用户名和pass都是ark，然后就能拿到控制台了，
可以看到gcc、cmake、git、apt都是自带的，
arkos实际对应的是rg351mp，默认的ark用户
应该就是最高权限可执行sudo的
```
* see https://github.com/dov/r36s-programming  
* RGB10X and R36H ssh is also ark/ark, support apt, gcc is gcc9, need to enable remote service from 'main menu->configuration'      
```
隔了很久，我终于拿到RGB10X掌机ArkOS系统的ssh了（用户和R36S一样，都是ark/ark，
方法也一样，用OTG线接USB转网口，接网线到路由LAN口即可），
但必须在主菜单配置中使能远程服务，效果如下，
甚至支持用浏览器打开ssh的网址80端口来获得一个网页文件管理器，
虽然没什么用

R36H也可以用相同的方法获取ssh  
```

## r36s test path  
* Put to ports/ons folder (but it is not launched from PORTS of main menu, just launched from file manager)    
  
## (TODO) How to launch from ports folder  

## (TODO) Third party supported OS firmware of R36H (and of R36S V5), but not tested with this ONScripter-Jh repo  
```
PAN4ELEC (Custom AmberELEC for Panel 4 Devices)
Unofficial AmberELEC build by KEgg for the most recent Panel 4 (V5) devices
```
* https://handhelds.wiki/R36S_Custom_Firmware
* https://github.com/tech4bot/r35s/releases/download/20240515/cHAos-R3xS.aarch64-20240515.img.gz  
* https://github.com/tech4bot/r35s/releases/download/20240515/cHAos-R3xS.aarch64-20240517.img.gz   
* (also support G350 but file different) https://github.com/Kegg1701/P4ELEC/releases/download/20250315/PAN4ELEC-RG351MP.aarch64-20250315.img.gz  
* (choose P4/V5 to download) https://github.com/AeolusUX/ArkOS-R3XS/releases/tag/ArkOS.V2.0.4302025  
* https://github.com/manster-zz/R36S-LINKS/wiki  
```
我测试过大部分R36S/RG351MP/RGB10X刷机包都用不到R36H，只有这几个可以：
cHAos-R3xS（0515和0517都可以），PAN4ELEC-RG351MP，
ArkOS_R35S-R36S_v2.0的P4版（不带P4的用不了）
```

## My checked and supported wireless net wifi modules 
* (recommended RTL8821CU) LB-LINK BL-WN650BT AC650  
RTL8821CU  
Realtek 8821CU Wireless LAN 802.11ac USB NIC  
RTL8821CU see also: https://www.hardkernel.com/shop/wifi-module-5bk/  
```
WIFI Module #5BK uses the same chipset (Realtek RTL8821CU) as WIFI Module #5B, 
so it is 100% compatible. IEEE 802.11ac/a/b/g/n WLAN and Bluetooth  
combo module with on-board 2.4Ghz and 5.8Ghz Dual band antenna.  
```

* 亮科(not高科)  
MT7601u ? (not this?), should be MT7662  
802.11n USB Wireless LAN Card  
