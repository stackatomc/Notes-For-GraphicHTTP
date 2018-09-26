# 第4章 HTTP状态码

标签：计算机网络

---

- 状态码的类别
	- 1xx Informational(信息性状态码) 接受的请求正在处理
	- 2xx Success 请求正常处理完毕
	- 3xx Redirection(重定向状态码) 需要进行附加操作以完成请求
	- 4xx Client Error(客户端错误状态码) 服务器无法处理请求
	- 5xx Server Error(服务器错误状态码) 服务器处理请求出错
- 常用的14个状态码简记
	- 200 OK
	- 204 Not Content：简单记就是没有资源可返回，该状态码代表服务器接受的请求已经成功处理，返回的相应报文中不含实体的主体部分
	- 206 Partial Content：表示客户端继续宁了范围请求，响应报文中包含由Content-Range指定范围的实体内容
	- 301 Moved Permanently
	- 302 Found 临时改变
	- 303 See Other 表示由于请求对应的资源存在着另一个URI，应使用GET方法定向获取请求的资源
	- 304 Not Modified 表示服务器端资源未改变，可直接使用客户端未过期的缓存
	- 307 Temporary Redirect 同302 Found，尽管302标准禁止POST变换成GET，但实际使用时大家并不遵守。而307则回遵照浏览器标准，不会从POST变成GET
	- 400 Bad Request 该状态吗表示i请求报文中存在语法错误，当错误发生时，需要修改请求的内容后再次发送请求
	- 402 Unauthorized 表示需要由通过HTTP等的认证信息，另外若之前已经进行过1次请求，则表示用户认证失败
	- 403 Forbidden 服务器端没有必要给出拒绝的详细理由，比如未获得文件系统的访问授权，访问权限出现某些问题（从未授权的发送源IP地址试图访问）等列举的情况都可能使发生403的原因
	- 404 Not Found
	- 500 Internal Server Error 表明服务器端再执行请求时发生了错误，也有可能是Web应用存在的bug或某些临时的故障
	- 503 Service Unavailable 表明服务器者暂时处于朝服在或者正在进行停机维护，现在无法处理请求。如果实现得知接触以上状况需要的时间，最好写入Retry-After首部字段再返回给客户端