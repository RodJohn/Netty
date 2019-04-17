# Netty


# 学习路程

张龙 精通并发与netty

遇到源码
http://svip.iocoder.cn/categories/Netty/



# 入门

```

建立服务端
设置channelinit
pipline设置handle
字符集handle
处理channel事件
接收发送消息
channelGroup


建立客户端
发送数据

http的客户和服务端demo
建立的流程


# 样例

socket

心跳超时

	客户端退出  tcp 已经建立好长连接  强制关机   remove  不会触发
	ideastateevent

websocket 
	
	解决http  
		无状态  cookie tooken 
		请求响应模型   不能双工通信 连接保持 （http1.1）   html5  
		
		例如网页聊天
		8 轮询 实时性  无效性 （没数据  不需要的头信息）

	过程
		通过http链接发送请求 请求头101  并升级协议 请求头 upgrade  
		7frame 数据帧
	
	httpobjectaggre处理

	websocketserveprotocal
	
	8Html5刷新页面 重新建立链接
	

```	

# protocobuf

序列化反序列化的库 也叫做编码和解码

RMI  
	remote method invocation
	远程方法调用
	只适合java
	
client 
server

RPC
	
remote process invitation 
	
/	
	
	

