QSocket5Tunnel 
-----------------------------
    是一个基于Qt的QTcpSocket和QTcpServer写的一个socket5代理的数据中转软件。
    分为客户端和服务端两部分，客户端负责本地建立socket5代理，服务端负责负责请求代理客户端需要请求的数据。
    其中客户端和服务端用一个TCP长链接链接。
    其中不用socket5的认证，自己单独的认证

---------------------------------   
    已知问题：服务端关闭时，由于垮线程释放socket，有错误提示。
                线程模型问题，需要解决
----------------------------------------

#TODO:
##TODO: next:
* 添加加密，安全和快速的加密算法(完成)
* 优化下服务端的进程架构，尽量直接线程建立socket，取消用moveToThread
* 服务端替换底层事件循环系统，用libev的事件替换，这样在linux，bsd，mac下就能有更好的性能。
* 测试压缩，看下性能，考虑是否压缩传输数据。

##TODO: Future
* 登录认证模块独立出来，动态返回服务器地址，多服务器的话，可以达到负载均衡
* 服务端加上数据库，管理用户和token，也可以登录用http，和http交互。
* 如果用户系统完善，添加流量统计。
* 客户端界面设计优化
* 考虑加入其他代理协议。
* 如果有效率更高的，更换数据序列化，和传输的数据结构。
