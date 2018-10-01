# 第9章 基于HTTP的功能追加协议

标签：计算机网络

---

- 消除HTTP瓶颈的SPDY
	- 新增加的协议支持：
	- 多路复用流：可以在一个TCP连接上处理多个并行的HTTP请求.TCP处理效率得到提高
	- 赋予请求优先级
	- 压缩HTTP首部
	- 推送功能：不用等客户端请求，服务器可主动发送数据
	- 服务器提示功能：可以提示客户端请求所需的资源，由于客户端可以发现缓存中的资源，若已在缓存中，则避免发送不必要的请求
- 使用浏览器进行全双工通信的WebSocket通信协议
	- 在HTTP连接建立后，需要完成一次握手步骤。用到HTTP的Upgrade首部字段.`Upgrade=websocket connection=Upgrade`
	- JavaScript可调用The WebSocket API