# 第2章 简单的HTTP协议

标签：计算机网络

---

- 请求报文
	- 格式
	```
	GET /index.htm HTTP/1.1
	Host: hackr.jp
	Connection: keep-alive
	Content-Type: application/x--www-form-urlencoded
	Content-Length: 16
	```
	请求报文由请求方法、请求uri、协议版本、可选的请求首部字段和内容实体构成的
	- 若请求uri不是访问特定资源而是对服务器吧恩深发起请求，可以用* 代替请求URI. 
		- 如`GET * HTTP/1.1`
- 响应报文
	- 格式
	```
	HTTP/1.1 200 ok
	Date: Tue, 10 Jul 2012 06:50:15 GMT
	Content-Length: 362
	Content-Type: text/html

	<html>
	```
	- 响应报文由协议版本、状态码、用以解释状态码的原因短语、可选的相应首部字段以及实体主体构成
- HTTP的无状态特点
	- HTTP是一种不保存状态，即无状态协议，HTTP协议自身不具备保存之前发送过的请求或相应的功能
	- 引入Cookie技术，实现了期望的保持状态功能
- HTTP/1.0和HTTP/1.1支持的方法
	- GET 获取资源
	- POST 传输实体主题
	- PUT 传输文件
	- HEAD 获得报文首部
	- DELETE 删除文件
	- OPTIONS 询问支持的方法
	- TRACE 追踪路径
	- CONNECT 要求用隧道协议连接代理
	- LINK 建立和资源之间的练习
	- UNLINK 断开连接关系
	- 注意
		- LINK和UNLINK在HTTP/1.1后已被废弃，不再支持
		- PUT、DELETE自身不带验证机制，任何人都可以操作，存在安全性问题，因此一般的Web网站不适用该方法。若配合Web应用程序的验证机制，或架构设计采用REST（表征状态转移）标准的同类Web网站，才可能会使用
		- TRACE可以用于查询发送出去的请求是怎样被加工修改的。因为，请求想要连接到原目标服务器可能通过代理中转，TRACE方法可用来确认连接过程中发生的一系列操作，让Web服务器端将之前的请求通信环回给客户端的方法。但是TRACE不常用，加上它容易导致XST（跨站追踪）攻击，通常就更不会用到了
		- CONNECT方法主要用于在与代码服务器通信时建立隧道，实现用隧道协议进行TCP通信。主要使用SSL和TLS协议吧通信内容加密后经过网络隧道传输
- 其他一些参数
	- 持久连接`Connection: keep-alive`
	- 管线化：管线化方法可不需要像从前发送请求后需要等到并收到相应，才能发送下一个请求。管线化技术出现后，不用等待响应亦可直接发送下一个请求
