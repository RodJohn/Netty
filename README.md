
# [图谱](https://www.processon.com/mindmap/5cb68333e4b06bcc137f0e34)

# Netty


# 学习路程

张龙 精通并发与netty

遇到源码
高屋建瓴的讲解 
适合于复习  而不利于第一次去理解源码
http://svip.iocoder.cn/categories/Netty/

https://zhuanlan.zhihu.com/p/63217085

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

# RPC

RMI  
	remote method invocation
	远程方法调用
	只适合java
	
client 
server

RPC

remote process invitation 
	跨语言
过程
	定义接口
	通过RPC编译器生成两端代码
	两端引入代码

RPC效率高
通过序列化的方式传输快
通过socket传输

#  protocolbuf

用于作为传输消息的载体
序列化反序列化
体积小速度快支持多种语言
定义
https://www.jianshu.com/p/6c9f90538efe
生成文件 不要去修改


# netty+procoBuffer

使用

netty原生支持procobuffer
https://www.jianshu.com/p/6102cc52b8fe
通过4个handle将数据进行编码和解码

解码
传递多种类型对象
多种传输类型的处理方式
自定义解析器
oneof

同步中间码
client和server间同步protobuffer
git subtree中间代码的管理
打包传递到maven


# thrift

Thrift是一款由Fackbook开发的可伸缩、跨语言的服务开发框架 完整的RPC框架

# gRPC

protobuffer可以作为IDR和编码方式



 
 





没有路由


# netty

简单的封装

EventLoopGroup
事件循环组
不断地轮询channel中的事件
用一个线程

register 
	Future
	Promise

EventExcuteGroup
next

NioEventLoopGroup
selectorProvider

newChild
newDefaultTHreadFactory

线程的创建和执行分离
Execute
execute
ThreadPerTaskExecute
DirectExecute
SerialExecute
ExecuteService
命令模式 委托模式
	


ServerBoostrap
Boostrap

ServerChannel

ServerSocketChannel 
是 netty定义的不是 javanio的



NioServerSocketChannel
use NIO selector based implementation to accept new connections.

bind

转发  工作


	
	
# Future


java utc Future

A {@code Future} represents the result of an asynchronous
{@code get} when the computation has completed, blocking if necessary until it is ready.

isDone

不知道什么时候该去调用get

Future<V> 

 Future<V> addListener(GenericFutureListener<? extends Future<? super V>> listener);
 
 isSucces
 
 sync
 Waits for this future until it is done,
 
 await
 
 ChannelFuture
 
 
 
