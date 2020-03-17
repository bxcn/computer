虚拟专网VPN（Virtual Private Network）属于远程访问技术，简单地说就是利用公用网络架设专用网络。例如某公司员出差到外地，他想访问企业内网的服务资源，这种访问就属于远程访问。VPN技术在企业网络中有关广泛的应用，可以通过服务器、硬件和软件等多种方法实现。

### VPN简介  
VPN是在公网网络中，按照相同的策略和安全规则，建立私有网络链接，


![image.png](https://upload-images.jianshu.io/upload_images/5177180-eba43648261856a2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)  

在传统的企业网络配置中，要进行远程访问，方法是租用DDN(数字数据网)专线或帧中继，这样的通信方案必然导致高昂的网络通信和维护费用。对于移动用户(移动办公人员)与远端个人用户而言，一般会通过拨号线路进入企业的局域网，这样必然带来安全上的隐患。VPN技术使得数据通信都进行了加密处理，有了数据加密就可以认为数据是在一条安全的传输通道上进行传输，就如同专门架设了一个专用网络一样。

#### VPN特点  
VPN技术从一定角度解决了数据传输的安全总是，有如下优点。
- 灵活性：VPN能够让移动员工、远程员工、合作伙伴等利用高速的宽带网络连接到企业网络，保证数据传输的安全性能。
- 费用低：VPN技术利用两万的宽带网络建立虚拟通道，不需要额外的铺设网络，因此费用较低。
- 可扩展性：设计良好的VPN是模块化和可升级的，VPN使企业使用ISP网络，可让用户更容易使用设置的互联网基础设施，快速地让新用户添加到网络。
- 拓扑管理：VPN技术可以让自己完全掌握自己网络的控制权，网络管理变化可以由自己管理。


但是VPN技术也有一些缺陷。例如，企业不能直接控制基于互联网的VPN可靠性和性能；创建VPN线路并不容易，这需要用户高水平的理解网络和安全问题； 需要认真地规划和配置； 不同厂商的VPN解决方案有兼容问题，等等； 


#### VPN类型  
根据不同的分类标准，VPN可以按以下3个标准进行划分。
1、按照VPN的协议分类
VPN的隧道协议主要有L2TP（Layer 2 Tunnel Protocol）、PPTP(Point to Point Tunnel Protocol)、L2F(Layer 2 Forwarding)和IPSes（IP Security Protocol）3种。其中，L2TP、PPTP和L2F协议工作在OSI模型的第二层，又称为隧道协议； IPSec是第三层隧道协议。


2、按照VPN拓扑分类  
按照拓扑可以分为以下两种，如图
![image.png](https://upload-images.jianshu.io/upload_images/5177180-3f9d5bdf2767df8b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- Remote Access VPN(远程接入VPN):客户端到网关，使用公网作为骨干网在设备之间传输VPN数据流量。
- Site to Site VPN(站点到站点VPN):网关到网关，通过公司的网络架构连接来自同公司的资源。

3、按照实现原理分类  
按照实现原理不同，可分为以下两种  
- 重叠VPN：此VPN需要用户自己建立端节点之间的VPN链路，主要包括GRE\L2TP\IPSec等众多技术。
- 对等VPN：由网络运营商在主干网上完成VPN通道的建立，主要包括MPLS VPN技术。


#### VPN工作原理  
VPN的基本工作过程如下图。数据由源端出发，经过访问控制、报文加密、报文认证、封装后进入隧道，到达目的地后进行数据的解封装、认证、解密等过程，而整个过程涉及的技术有安全隧道技术、信息加密技术、用户认证技术及访问控制技术。

![image.png](https://upload-images.jianshu.io/upload_images/5177180-524325c7024858a4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

1、安全隧道技术  
为了在公网上传输私有数据，必须进行“信息封装（Encapsulation）”。在Internet上传输的加密数据包中，只有VPN端口或网关的IP地址暴露在外面，如图
![image.png](https://upload-images.jianshu.io/upload_images/5177180-49abc1c362c8669e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

目前按照协议分为二层隧道和三层隧道。第二层隧道协议，建立在点对点协议PPP的基础上，先把各种网络协议（IP、IPX）封装到PPP帧中，再把整个数据帧装入隧道协议，此类隧道适用于公共电话交换网或ISDN线路链接的VPN，如图
![image.png](https://upload-images.jianshu.io/upload_images/5177180-fd02b3c1f41e92c6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
第三层隧道协议把各种网络协议直接装入隧道协议，在可扩充性、安全性、可靠性方面优于第二层隧道协议，如图
![image.png](https://upload-images.jianshu.io/upload_images/5177180-6a8aa137ddda0f21.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


2、信息加密技术  
数据加密主要是确保数据的安全。一种方法是保护算法，加密系统的安全性能基于算法本身的保密，算法代码必须被严格保护起来，如果算法泄露，所有相关方必须改变算法。第二种途径是保护密钥，对于现代密码术，所有的算法都是公开的，由密码密钥确保数据的安全。密钥是一个比特序列，它与被加密的数据一起被输入一个加密算法。

两种基本类别的加密算法被用于保护密钥：对称和非对称。

对称加密使用相同的密钥对数据进行加密和解密，如下图。使用的对称密钥一般需要提前共享。对称加密有以下特点：
- 通常加密比较快（可以达到线速）
- 基于简单的数学操作（可借助硬件）
- 用于大批加密
- 密钥的管理是最大的问题  

![image.png](https://upload-images.jianshu.io/upload_images/5177180-01cf25df6391fd1f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240) 

非对称加密算法使用不同的密钥进行加密和解密数据，每一方都有两个密钥，即公钥和私钥。其中，公钥可以公开； 私钥必须安全保存。其中一个密码用于加密，一个用于解密，其算法在运行速度上远低于对称加密算法。非对称加密算法包括公钥和私钥签名两种方法，如图

![image.png](https://upload-images.jianshu.io/upload_images/5177180-dd4b3785f526995c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### IPSec  

IPSec(IP Security)是IETF为保证在Internet上传送数据的安全保密性，而制定的框架协议，各算法之间相互独立，应用在网络层，保护和认证IP数据包IPSec可以从传输层至应用层实现保护，所以IPSec几乎可以保护所有的应用流星。

1、工作模式  
IPSec支持隧道模式和传输模式  
- 隧道模式：IPSec对整个IP数据包进行封装和加密，隐蔽了源目的IP地址，从外部看不到数据包的路由过程。
- 传输模式：IPSec只对IP有效数据载荷进行封装和加密，IP源目的IP地址不加密传送，安全程度相对效低。
- 
2、IPSec框架  
IPSec框架提供了信息的机密性、数据的完整性、用户的验证和防重放保护，包含以下2个组件。
- 安全协议：IPSec提供两个安全协议，即AH(Authentication Header)认证协议和ESP(Encapsulation Security Payload)封装安全载荷协议，AH和ESP的隧道模式封装如下图。
- 加密算法：IPSec使用的加密算法很多，如DES\3DES\AES等，用户可以根据需求选择合适的加密算法。
- 认证算法：确保数据的完整性，使用MD5或SHA认证算法。
- 共享密钥：一般有两种方法，预共享密钥或使用RSA的数字签名
- DH算法组：一般有3种DH密钥交换算法，包括DH Group1(DH1)、DH Group2(DH2)和DH Group5(DH5).

![image.png](https://upload-images.jianshu.io/upload_images/5177180-178029fa206ebf17.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

3、安全联盟  
两个设备之间的协商参数被称为安全联盟SA(Security Association),建立SA是其他IPSec服务的前提。一个SA通常包含以下安全参数。
- 认证/加密算法、密钥长度及其他的参数。
- 认证主加密所需要的密钥  
- 哪些数据要使用该SA
- IPSec的封装协议和模式  


4、IKE  
IPSec使用Internet密钥交换IKE(Internet Key Exchange)协议来建立密钥交换过程。IKE在RFC2409中定义，它是一种混合协议，结合了Internet联盟和密钥管理协议ISAKMP(Internet Secuity And Key Management Protocol)等多种协议每个对等体必须由相同的ISAKMP和IPSec参数来建立一个安全的VPN.

在两个对等体之间建立一条安全通信隧道，IKE协议执行两个阶段。

(1)IKE阶段1
阶段1的基本目的是协商IKE策略集，认证对等体并在对等体之间建立一条安全通道，它可以使用主模式（）和主动模式（）完成。阶段1确定IKE通信安全的算法、散列及其他参数，阶段1发生3次交换。
- 第一次：对等体协商确定用于保护IKE通信安全的算法和散列。
- 第二次：对等体之间创建和交换DH公钥。DH组1产生768bit密钥，DH组2生产1024bit密钥，DH组5生产1536bit密钥
- 第三次：认证远端的对等体，使用PSK、RSA签名或RSA加密随机数

(2) IKE阶段2  
由IKE进程ISAKMP代表IPSec进行SA协商。



#### GRE隧道  
能用路由封装GRE(Generic Routing Encapsulation)协议用来对任意一种网络层协议（IPv6）的数据报文进行封装，使这些被封装的数据报文能够在另一个网络（如IPv4）中传输。其包头如图：  
![image.png](https://upload-images.jianshu.io/upload_images/5177180-6b5a9d5912a366e5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

封装前后数据报文的网络层协议可以相同，也可以不同。封装后的数据报文在网络中传输的路径，称为GRE隧道。GRE隧道是一个虚拟的点到点的连接，其两端的设备分别对数据报文进行封装及解封装，GRE封装后的报文包括如下3部分。
(1)净荷数据（Payload packet）
需要封装和传输的数据报文。净荷数据的协议类型称为乘客协议（Passenger Protocol）乘客协议可以是任意的网络层协议。

(2)GRE头（GRE header）
采用GRE协议对净荷数据进行所添加的报文头，包括封装层数、版本、乘客协议类型、校验和信息、Key信息等内容。添加GRE头后的报文称为GRE报文。对净荷数据进行封装的GRE协议，称为封装协议（Encapsulation Protocol）

(3)传输协议的报文头（Delivery header）
在GRE报文上添加报文头，以便传输协议对GRE报文进行转发处理。传输协议（Delivery Protocol或Transport Protocol）是指负责转发GRE报文的网络层协议。设备支持IPv4或IPv6两种传输协议：当传输协议为IPv4时，GRE隧道称为GRE over IPv4隧道。当传输协议为IPv6时，GRE隧道称为GRE over IPv6隧道。
