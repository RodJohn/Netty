
https://www.cnblogs.com/luxiaoxun/archive/2015/03/11/4331110.html



nio 没有 的eventhandle
netty 进行了封装

过程

两个reactor 

main只负责accept

IO操作把可能阻塞的线程放在work

main把连接移交给sub



