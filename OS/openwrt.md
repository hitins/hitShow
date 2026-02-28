# OpenWrt


#linux

## Install

1. 下载 OpenWrt 固件: 进入[官方固件 Web](https://firmware-selector.openwrt.org), 选择固件版本和设备.
	1. 选择下载默认固件.
	2. 选择在线编译固件: 推荐, 通常移除 pppoe, 添加 dnsproxy.
2. 安装 OpenWrt
	1. Web 界面 Update 安装.
	2. 方式 2 TF卡安装: 安装后 TF 卡需扩容.
	3. KVM 安装: 推荐用 incus、物理网卡、Bridge 虚拟网卡.

			```
			# lan 口, 局域网, 禁止物理接口自动获取 IP
			brctl addbr vln
			brctl addif vln eth0
			# wan 口, 禁止物理接口从上游自动获取 IP
			brctl addbr vmn
			brctl addif vmn eth1	
			``` 
