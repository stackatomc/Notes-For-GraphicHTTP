# 第1章 了解Web及网络基础

标签：计算机网络

---

- TCP/IP
	- 概念：把与互联网相关联的协议集合起来总称为TPC/IP
	- 分层：TCP/IP协议族里重要的一点就是分层。TCP/IP协议族按层次分别分为以下4层：应用层、传输层、网络层（网络互连层）和链路层（又称数据链路层、网络接口层）
	- 分层好处：若互联网只由一个协议统筹，某个地方需要改变设计时，就需要把所有部分整体替换掉。而分层之后只需要把变动的层替换掉
	- TCP/IP通信传输流
	```
	应用层 (HTTP数据)
				
	传输层 (TCP首部(HTTP数据))
			加入TCP首部后向下发
	网络层 (IP首部(TCP首部(HTTP数据)))
			加入IP首部后向下发
	链路层 以太网首部(IP首部(TCP首部(HTTP数据)))
	```	
	- 几个重要概念
		- IP协议、IP地址、MAC地址、ARP协议、RARP协议、路由选择、负责域名解析的DNS服务
	- TCP协议
		- 注意三次握手的过程：TCP标志SYN(synchronize)和ACK(ACKNOWLEDGEMENT)
- URI和URL
	- URI统一资源标识符，用字符串标识某一互联网资源，而URL表示资源的地点(互联网上所处的位置)
	- 除HTTP协议外，其他常用的协议有ftp,mailto,file...