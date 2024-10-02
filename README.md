﻿# onscripter-jh-r36s
[WIP] My ONScripter-jh R36S port

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

## Cross compile gcc toolchain and stage files    
* aarch64-buildroot-linux-gnu_sdk-buildroot.tar.gz  
from rg351p-toolchain,  
https://github.com/AdrienLombard/sm64-351elec-port/releases/tag/v1.0.0  

## TODO and bugs   
* Check key map  
