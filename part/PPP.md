### PPP简介

点对点（PPP， Point to Point）协议是用于在两个节点之间传送帧的协议。PPP标准有IETF的RFC定义。PPP是一种用于广域网的数据链路层协议，可在多种串行WAN中实施，可用于各种物理介质，包括双绞线、光缆、卫星传输及虚拟连接。PPP可用于承载多种三层协议，如 IPv4、IPv6和IPX。

#### PPP协议  
PPP协议主要包括以下协议： 
- 链路控制协议（LCP, Link Control Protocol）：用来建立、拆除和监控数据链路。
- 网络控制协议（NCP, Network Control Protocol）：用来协商在数据链路上所传输的网络层报文的一些属性和类型。
![PPP链路建立过程](https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=1312658320,385303298&fm=15&gp=0.jpg)



#### PPP帧格式  
![PPP帧格式](https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=2679931486,1789829540&fm=15&gp=0.jpg)

- 标志（F）:1字节，填充0x7E，用来标示PPP帧的开始和结束  
- 地址（A）:1字节，对方的数据链路层地址，因为PPP协议是点对点的链路层协议，所以此地址无意义，用0xFF填充。  
- 控制（C）:1字节，填充0x03。
- 协议：2字节，用于标志PPP数据帧中信息域所承载的数据报文内容，常见取值如0xc021,表示LCP；0xc023,表示PAP; 0xc223，表示CHAP；0x8021，表示NCP； 0x0021,表示IP协议数据报文。
- 帧校验（FCS）：2字节，用于PPP帧检查。  

#### PPP认证  
PPP协议支持用户的认证，是广域网接入使用的最广泛协议，目前PPP用的最多的两种协议认证是口令认证协议（PAP，Password Authentication Protocol）和质询握手认证协议（CHAP, Challenge  Handshake Authentication Protocol）认证  

1、PAP认证  
PAP为两次握手协议，它通过用户名和密码来对用户进行认证。PAP在网络上以明文的方式传递用户名和密码，如果认证报文在传输过程中被截获，便有可能对网络安全造成威胁。因此，它适用于对网络安全要求相对较低的环境。

2、CHAP认证  
CHAP为三次握手协议，CHAP认证过程分为两种方式：认证方配置了用户名、认证方没有配置用户名。推荐使用谁方配置用户名的方式，这样被认证方可以对认证方的身份进行确认CHAP只在网络上传传输用户名，并不传输密码（准确地讲，它不直接传输用户密码，传输的是用MD5算法将用户密码和一个随机报文ID一起计算的结果），因此它的安全性要比PAP高，其工作过程如下图。


#### MLP  
MLP(MultiLink PPP)可以将多条PPP链路捆绑起来。对于MLP链路两端设备，就好像只有一条PPP连接，只需配置一个IP地址。MLP具有以下优点。
- 增加带宽  
- 负载分担  
- 降低时延  











