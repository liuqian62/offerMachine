## 目录
- [OSI七层模型？](#osi七层模型)
- [有连接，无连接，可靠协议，不可靠，有状态，无状态的区别?](#有连接无连接可靠协议不可靠有状态无状态的区别)
- [简述HTTP协议?](#简述http协议)
- [GET和POST有什么区别？](#get和post有什么区别)
- [301和302状态码的区别？](#301和302状态码的区别)
- [从输入URL到页面加载发生了什么？（HTTP的工作原理？）](#从输入url到页面加载发生了什么http的工作原理)
- [HTTP长连接和短连接的区别？](#http长连接和短连接的区别)
- [HTTP是不保存状态的协议，那么如何保存用户的状态？（Cookie，Session的区别是什么？）](#http是不保存状态的协议那么如何保存用户的状态cookiesession的区别是什么)
- [如果Cookie被禁用怎么办？](#如果cookie被禁用怎么办)
- [HTTP1.0 和 HTTP1.1的主要区别是什么？](#http10-和-http11的主要区别是什么)
- [URI和URL的区别是什么？](#uri和url的区别是什么)
- [HTTP 和 HTTPS的区别是什么？](#http-和-https的区别是什么)
- [TCP协议是什么？](#tcp协议是什么)
- [简述TCP头部结构？](#简述tcp头部结构)
- [简述TCP三次握手与四次挥手？](#简述tcp三次握手与四次挥手)
- [为什么要三次握手？只有两次握手可以吗？](#为什么要三次握手只有两次握手可以吗)
- [三次握手过程中可以携带数据吗？](#三次握手过程中可以携带数据吗)
- [为什么连接的时候是三次握手，关闭的时候却是四次挥手?(为什么挥手需要四次，三次挥手不行吗？）](#为什么连接的时候是三次握手关闭的时候却是四次挥手为什么挥手需要四次三次挥手不行吗)
- [为什么客户端需要等待2MSL再关闭？](#为什么客户端需要等待2msl再关闭)
- [什么是半连接队列？什么是全连接队列？](#什么是半连接队列什么是全连接队列)
- [ISN是什么？是固定的吗？](#isn是什么是固定的吗)
- [SYN攻击是什么？(泛洪攻击是什么？)](#syn攻击是什么泛洪攻击是什么)
- [如果已经建立了连接，但是客户端突然出现故障了怎么办?](#如果已经建立了连接但是客户端突然出现故障了怎么办)
- [为什么会发生TCP粘包拆包？如何处理？](#为什么会发生tcp粘包拆包如何处理)
- [TCP协议如何保证可靠传输？](#tcp协议如何保证可靠传输)
- [简述UDP协议？UDP的头部结构？](#简述udp协议udp的头部结构)
- [TCP/UDP协议的区别](#tcpudp协议的区别)
- [简述IP协议？IP协议的头部结构？](#简述ip协议ip协议的头部结构)
- [简述IP地址的组成？](#简述ip地址的组成)
- [0.0.0.0	与 127.0.0.1 与 localhost的区别?](#0000与-127001-与-localhost的区别)
- [NAT协议的作用？（公网与私网的区别？）](#nat协议的作用公网与私网的区别)
- [ARP协议是什么？](#arp协议是什么)

<br>

---------
## OSI七层模型？
从上往下依次为：
>**应用层->表示层->会话层->传输层->网络层->数据链路层->物理层**



![在这里插入图片描述](https://img-blog.csdnimg.cn/20201028083953689.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1dvcnRoeV9XYW5n,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020102808542356.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1dvcnRoeV9XYW5n,size_16,color_FFFFFF,t_70#pic_center)

<br>

<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


-------------

## 有连接，无连接，可靠协议，不可靠，有状态，无状态的区别?
* **不可靠**：不能保证数据安全准确的传输给对方，提供“尽力而为”的交付服务。

* **可靠**：保证数据安全准确的传输给对方。

* **有连接**：数据发送方与数据接收方需要建立对话并维持该来连接。

* **无连接**：数据发送方与数据接收方不需要建立对话并维持该连接。

* **有状态**：对于事务处理拥有记忆能力，对于之前处理过的事务保留其信息。

* **无状态**：对于事务处理没有记忆能力，对于之前处理过的事务不再保留其信息。

<br>

<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


-------------
## 简述HTTP协议?

>**HTTP（超文本传输协议）是应用层上的一种基于C/S架构的无连接无状态的请求/响应模式通信协议。**

HTTP有**请求报文**和**响应报文**两种形式。

<br>

* **请求报文**

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201028091449264.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1dvcnRoeV9XYW5n,size_16,color_FFFFFF,t_70#pic_center)

请求报文由四个部分组成： 

> **请求行 + 请求头 +  空行+ 请求体** 

1.	 **请求行**

**1.1 请求方法**

GET：重点在于从服务器上获取资源。

POST: 重点在于向服务器发送数据（例如提交表单或上传文件）

HEAD: 类似于GET请求，不过返回的响应报文中没有响应体承载数据，只用于获取响应报头。

**1.2 URL：统一资源定位符**

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201028091718380.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1dvcnRoeV9XYW5n,size_16,color_FFFFFF,t_70#pic_center)

**1.3	协议版本**

有HTTP1.0 ， HTTP1.1， HTTPS 等协议

2.	**请求头**

通过键值对的方式存储。常见的如Content-Type（请求体/响应体的类型），Content-Length（请求体/响应体的长度），Content-Encoding（请求体/响应体的编码格式）

3.	**空行**

用于区分请求体

4.	**请求体**

用于存放实际的数据

<br>

* **响应报文**

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201028092542784.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1dvcnRoeV9XYW5n,size_16,color_FFFFFF,t_70#pic_center)

响应报文同样分为四个部分：
**状态行 + 响应头 + 空行 + 响应体**

1.	**状态行**

1.1	**协议版本**

一般跟请求报文对应的协议版本相同，有HTTP1.0，HTTP1.1，HTTPS。

1.2	**状态码**

HTTP状态码有五种类型，如下：

>1**：信息，服务器收到请求，要求请求者继续操作；

>2**：成功，操作成功接收并处理；200 OK：客户端请求成功；

>3**：重定向，需要进一步的操作以完成请求；301：网页被永久转移到其他URL；302：网页临时跳转。

>4**：客户端错误，请求包含语法错误或无法完成请求；400 Bad Request：客户端请求有语法错误，不能被服务器所理解；401 Unauthorized：请求未经授权；404：请求资源不存在，可能输入了错误的URL。

>5**：服务器错误，服务器在处理请求的过程中发生了错误。500：服务器内部发生了不可预期的错误；503 Server Unavailable：服务器当前不能处理客户端的请求。

更多状态码可见：
https://www.runoob.com/http/http-status-codes.html

1.3	**状态码信息**

如 200 OK，404 NOT FOUND。

2.	**响应头**
>一般以键值对的方式进行存储。常见的如Content-Type（请求体/响应体的类型），Content-Length（请求体/响应体的长度），Content-Encoding（请求体/响应体的编码格式）。

3.	**空行**
>用于划分开响应头和响应体。

4.	**响应体**
>用于存放响应数据。

<br>

* **请求报文与响应报文样例**

1. **请求报文GET**

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201028092958816.png#pic_center)

2. **请求报文 POST**

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201028093004438.png#pic_center)

3. **响应报文 返回json字符串**

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201028093015348.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1dvcnRoeV9XYW5n,size_16,color_FFFFFF,t_70#pic_center)

4. **响应报文 HTML**

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201028093021341.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1dvcnRoeV9XYW5n,size_16,color_FFFFFF,t_70#pic_center)

<br>




<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


-----------
## GET和POST有什么区别？
1.	GET重点在从服务器获取数据；POST重点在于向服务器发送数据。

2.	GET和POST都能够使用额外的参数，GET的参数出现在URL之中并用`？`隔开，参数之间用`&`相连，是可见的；POST提交的数据是放在请求体中，是不可见的。

3.	GET传输数据时会有安全问题，在提交数据时用户名和密码都会出现在URL上面，黑客可以轻松获得；而POST方法提交的数据由于是存放在请求体中，不会被显示。

4.	GET传输数据大小有限制（因为浏览器对URL长度有限制）；POST方法传输的数据没有限制。

* **GET 和 POST样例补充**

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201028093851432.png#pic_center)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201028093857249.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1dvcnRoeV9XYW5n,size_16,color_FFFFFF,t_70#pic_center)

<br>


<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


-----------
## 301和302状态码的区别？ 

* 301（Moved Permanently）状态码代表网页被永久转移到其他URL；302（Found）状态码代表网页被暂时转移到其他URL。


<br>



<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


--------------
## 从输入URL到页面加载发生了什么？（HTTP的工作原理？）
1.	浏览器向`DNS（Domain Name Server）`请求，DNS将域名转换为对应的IP地址。

2.	浏览器连接到Web服务器`HTTP/80`端口，三次握手创建TCP连接。
3.	浏览器发送HTTP请求，读取URL域名后面对应文件，并注意该请求作为TCP三次握手中的第三次握手的数据发送给Web服务器。
4.	服务器接收HTTP请求并返回HTTP响应，响应体中存放对应的`html`文本。
5.	如果CONNECITON模式为`close`， 立刻四次挥手释放TCP连接；若CONNECTION模式为`keep-alive`，则保持该连接一段时间后再释放，这段时间内还可以接受请求。
6.	浏览器解析`html`文本内容并显示。

<br>


<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


--------
## HTTP长连接和短连接的区别？
* **长连接**
CONNECTION字段设置为`keep-alive`，在建立连接，传输数据之后，并不会马上断开连接，而是等待一段时间之后再断开，这段时间可以再多次传输数据。

* **短连接**
CONNECTION字段设置为`closed`，在建立连接，传输数据之后，立刻断开连接。会有较大的开销。

>**补充：
>1.HTTP1.0默认使用短连接，HTTP1.1默认使用长连接。**
>**2.长连接分为流水线方式和非流水线方式，非流水线方式就是在接收到HTTP的下一次响应之前都不能再发送新的请求报文，流水线方式就是在接收到HTTP下一次响应报文之前都可以发送新的请求报文。**



<br>

<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


----------

## HTTP是不保存状态的协议，那么如何保存用户的状态？（Cookie，Session的区别是什么？）
使用Cookie 和Session。
* **Session**

Session存储在服务器中，会为每一个用户都创建特定的sessionID并且保存对应数据，数据可以保存在内存或数据库中。

* **Cookie**

Cookie存储在客户端浏览器中，会记录下该浏览器对应的SessionID，并且 每一次HTTP请求都会把SessionID发过来，这样服务器就能识别该用户了；同样cookie也可以用来记录用户的信息，比如账户密码等。


<br>

<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


-----------
## 如果Cookie被禁用怎么办？
可用将URL重写，也就是将SessionID直接附加在URL路径的后面。

<br>

<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


-------------

## HTTP1.0 和 HTTP1.1的主要区别是什么？
1.	**长短连接**：HTTP1.0默认使用短连接；HTTP1.1默认使用长连接。

2.	**错误状态响应码**：HTTP1.1中新增了24个错误状态响应码。
3.	**缓存控制策略**：HTTP1.1中请求头中引入了更多的缓存控制策略。
4.	**断点续传功能**：HTTP1.1中请求头中引入了range，可以只请求资源的某个部分，实现断点续传。

<br>

<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


-----------------
##  URI和URL的区别是什么？
* **URI**
统一资源标识符（Uniform Resource Identifier），在某一种规则下能唯一的标识出一个资源。

* **URL**
统一资源定位符（Uniform Resource Location），用定位的方式唯一的标识出一个资源。

**URL就是用定位方式实现的URI。**

<br>

<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


------------
## HTTP 和 HTTPS的区别是什么？
详见网络安全专题。

<br>

<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


-----------------
## TCP协议是什么？
TCP协议是一个**面向连接**的，**可靠**的，**基于字节流**的**全双工端对端**通信协议。

**面向连接**的意味着数据发送方与数据接收方需要建立对话并维持该来连接。
**可靠**的意味着能保证数据安全准确的传输给对方。
**基于字节流**意味应用程序对于数据的发送和接收都是没有边界限制的。

>补充：**TCP基于字节流**/**UDP基于数据报**的理解，TCP传输的**send/recv**函数，UDP的**sendto/recvfrom**函数。
>![在这里插入图片描述](https://img-blog.csdnimg.cn/20201029100855856.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1dvcnRoeV9XYW5n,size_16,color_FFFFFF,t_70#pic_center)

<br>

<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


----------
## 简述TCP头部结构？

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201029103104560.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1dvcnRoeV9XYW5n,size_16,color_FFFFFF,t_70#pic_center)
TCP头部与IP数据报头部一样均为**20**个字节。

* **第一行**
>**源端口号（16bit） + 目的端口号（16bit）**：
**端口号用于区分同一个IP地址下的不同应用程序**。我们将 IP + Port 称为一个插口（Socket）。设立端口号的原因是同一个IP下可能运行了多个应用程序，如FTP（21），SMTP（25），SSH（22）等。


* **第二行**
>**序列号（32bit）**:
英文为seq，序列号的作用有两点，**一是保证数据包的传输顺序，二是避免因网络延迟带来的网络混乱**；客户端向服务器发送的序列号一般为ISN（initial sequence number） + 1；SYN和FIN会消耗掉一个序列号。

* **第三行**
>**确认号（32bit）**:
英文为ack，假设收到了ISN 为x的SYN报文，那么ack值就应该为x+1，**代表已经收到了该报文**。

* **第四行**
>**头部长度（4bit）**：最小为20字节（0101），最大为60字节（1111）
**保留（6bit）**
**标志位（6bit）**：
URG：紧急标志
ACK：确认标志，代表确认号是否有效
PSH：提示接收端应用程序应该立刻从TCP缓冲区读走数据，为后续接收数据腾出空间。
RST：复位报文段，要求重新建立连接
SYN：同步报文段，请求建立连接
FIN：结束报文段，通知对方本方将要关闭连接 
**窗口大小（16bit）**：英文名 window size，也可以称为滑动窗口，是TCP流量控制的手段，用于告诉对方TCP接收缓冲区还能够接收多少字节的数据，这样对方可以控制发送数据的速度。窗口大小实质上对应了内核socket接收缓冲区的大小。


* **第五行**
>**校验和（16bit）**：使用CRC算法检验TCP报文段 头部 + 数据 部分是否有损坏，保证了TCP的可靠传输。
**紧急指针（16bit）**：紧急指针相对当前序列号的偏移，URG置位1时才有效，目前已弃用，不做过多了解。

* **选项**：
>**是一个可变长的选项信息，最大为40个字节**。
>![在这里插入图片描述](https://img-blog.csdnimg.cn/2020102910330284.png#pic_center)
>其中kind表示选项的类型，length指定 选项 的总长度，info是选项的具体信息
>![在这里插入图片描述](https://img-blog.csdnimg.cn/20201029103317393.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1dvcnRoeV9XYW5n,size_16,color_FFFFFF,t_70#pic_center)
>![在这里插入图片描述](https://img-blog.csdnimg.cn/20201029103324330.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1dvcnRoeV9XYW5n,size_16,color_FFFFFF,t_70#pic_center)
>
<br>


<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


-----------------
## 简述TCP三次握手与四次挥手？
* **三次握手**

开始时客户端和服务器均处于 `CLOSED` 状态，在socket编程中，服务器 `listen()` 之后被动打开，客户端 `connection()` 之后主动打开，之后进行三次握手：



1. **第一次握手**

>客户端给服务器发送SYN报文，并指明客户端的ISN，此时客户端处于SYN-SENT状态。

TCP报文头部 SYN = 1 ， seq = x。

2. **第二次握手**

>服务器收到了客户端的SYN报文之后，会发送自己的SYN-ACK报文作为应答，在报文中指明了自己的ISN；此时服务器处于SYN-RCVD 状态。

TCP报文头部 SYN = 1， ACK = 1，seq = y， ack = x + 1。

3. **第三次握手**

>客户端接收到服务器的SYN之后，发送ACK报文作为应答发送后客户端进入 ESTABLISHED 状态，服务器收到ACK后也进入 ESTABLISHED 状态，双方开始数据交换。

TCP报文头部 ACK = 1， seq = x + 1，ack = y + 1。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200827112044355.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1dvcnRoeV9XYW5n,size_16,color_FFFFFF,t_70#pic_center)

<br>



* **四次挥手**

开始时客户端和服务端都处于`ESTABLISHED`状态，假设客户端先发起关闭请求进行主动关闭，服务端接收到通知后，进行被动关闭。
在网络编程中，任意一方执行 `close（）`操作，都会执行四次挥手。

1. **第一次挥手**

>客户端向服务端发送FIN报文，同时指定自己的序列号，此时客户端处于 FIN-WAIT1 状态。

TCP报文头部信息：FIN = 1，seq = u。

2. **第二次挥手**

>服务端接收到客户端的FIN报文后，发送ACK报文作为应答，服务端处于 CLOSE-WAIT 状态，客户端收到ACK后处于FIN-WAIT2状态，此时TCP处于半关闭状态，服务端仍然在向客户端发送数据。

TCP报文头部信息：ACK = 1，seq = v，ack = u + 1。

3. **第三次挥手**

>服务端发送完数据之后，向客户端发送 FIN-ACK报文，此时服务端处于 LAST-ACK 状态。

TCP报文头部信息：FIN =  1， ACK = 1，seq = w，ack = u + 1。


4. **第四次挥手**
>客户端接收到服务端的FIN-ACK报文后，发送ACK报文给客户端，此时客户端处于 TIME-WAIT 状态，需要等待 2MSL，之后进入CLOSED状态，服务端接收到ACK后也进入CLOSED状态。

TCP报文头部信息：ACK = 1，seq = u + 1， ack = w + 1。




![在这里插入图片描述](https://img-blog.csdnimg.cn/20200827183705300.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1dvcnRoeV9XYW5n,size_16,color_FFFFFF,t_70#pic_center)
<br>

>**补充**：
>SYN报文会消耗序列号，不能携带数据。
> FIN报文会消耗序列号，不能携带数据。
> ACK报文如果携带数据则会消耗序列号，如果不携带数据则不会消耗序列号。

<br>

<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


------------
## 为什么要三次握手？只有两次握手可以吗？
三次握手才能保证双方的接收发送能力都是正常的，第三次握手有**两点作用**：

1. 客户端的SYN报文因网络延时后滞后，此时客户端超时重传SYN报文并与服务器已经完成了数据的传输，随后第一次的SYN报文之后到达服务器，服务器误认为这是一次新的连接请求，于是发送SYN-ACK给客户端，并直接进入ESTABLISHED状态，但是客户端会直接忽略这一次SYN-ACK，导致死锁。

2. 如果第二次握手的ACK信号丢失，服务器直接进入ESTABLISHED状态，而客户端没有收到ACK信号，还处于SYN-SEND阶段，则会形成死锁。

<BR>


<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


----------
## 三次握手过程中可以携带数据吗？
 **第一次第二次握手不行，第三次握手可以**；

假如第一次握手可以携带数据，那么如果有人要恶意攻击服务器，会在SYN报文中存入大量数据，并疯狂发送SYN报文，服务器将会因处理这些报文陷入瘫痪。

第三次握手返回ACK报文时，双方连接已经建立，自然可以携带数据。

<br>


<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


------------
## 为什么连接的时候是三次握手，关闭的时候却是四次挥手?(为什么挥手需要四次，三次挥手不行吗？）

**挥手必须四次**，因为四次挥手中，服务器收到FIN后，并不能立刻返回FIN-ACK，而是先发送ACK，**也这是为什么挥手需要四次的原因，因为需要等到数据传输完成才行**，再发送FIN-ACK，这两个不能合到一起发送，所以需要四次挥手来关闭连接。

<br>


<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


--------------
## 为什么客户端需要等待2MSL再关闭？
原因有**两点**：

1. **保证客户端最后发送的ACK能够到达客户端**
如果这个ACK报文丢失，服务器超时重传FIN-ACK，客户端在2MSL的时间内一定可以接收到这个超时重传的FIN-ACK，这样可以避免服务器没有收到最后的ACK而空等待。

2. **防止旧连接中的报文影响新连接**
客户端在发送最后一个ACK后，等待2MSL，这样该连接中的所有报文都已经在网络中消失，不会影响到下一个新的连接。


<br>



<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


-----
## 什么是半连接队列？什么是全连接队列？
* **半连接状态**

**半连接状态**也就是服务器在进行第二次握手之后进入`SYN-REVD`的状态，并且这些连接由半连接队列存放。

* **全连接状态**

**全连接状态**也就是完成了三次握手的连接，全连接队列将存放这些连接。

<br>

<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


-----

## ISN是什么？是固定的吗？
>**ISN是TCP三次握手中为了建立连接而使用的一个初始序列号，ISN随时间而变化（每4ms加1），因此每一个连接都有不同的ISN。**

ISN不固定有两个好处：

1. 如果ISN固定，上一次连接的报文因网络延迟在这一次连接中到达，并恰好两次的seq相同，那么就会发生网络混乱。

2. 固定ISN容易遭受到黑客攻击，黑客能得知服务器的ISN，能在第三次握手正确的返回ACK报文，与服务器建立连接。

<br>

<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


---------
## SYN攻击是什么？(泛洪攻击是什么？)
>**黑客伪造大量不存在的IP地址，并不断向Server发送SYN请求，由于IP地址不存在，Server会不断发送SYN-ACK报文直至超时，这些伪造的SYN报文将导致半连接队列满，导致正常的SYN请求因无法加入半连接队列而被丢弃，这样会造成服务器瘫痪。**

常见的防御SYN攻击的方法有：

1.**过滤网关防护** ：如设置SYN代理，让代理为服务器处理SYN请求，如果收到了客户端的ACK包那么就向服务器完成三次握手。

2.**增大半连接队列容量**

3.**缩短超时时间与减少重传次数**

4.**SYNcookies技术**

<br>

<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


----------
## 如果已经建立了连接，但是客户端突然出现故障了怎么办?

服务端会有一个**Keep-Alive**心跳包机制，也就是**定期内会通过发送数据包检测客户端是否正常运行**，那么就认为客户端已经出现故障， 服务器自动断开。

<br>

<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


--------------
## 为什么会发生TCP粘包拆包？如何处理？
>**TCP粘包发生的原理是TCP传输是基于字节流的，发送端发送数据与接收端接收数据并没有边界，没有边界导致所有的数据粘合在了一起，也就发生了TCP粘包**。
>在socket编程中，假设发送方执行send操作x次，都只是将x次的数据发送到发送缓冲区中，真正发送到对端是由TCP协议来完成；而接受方执行recv操作y次之后将数据读取出来，并不是发送一次就对应着接受一次。

* **TCP粘包发生的原因**

1.	TCP发送缓冲区的数据堆积了很多之后才发送；

2.	TCP接收缓冲区的数据堆积了很多之后才接收；

* **TCP拆包发生的原因**

1.	待发送的数据部分大于MSS，需要进行拆分；

2.	待发送的数据部分大于发送缓冲区剩余空间大小，需要进行拆分。



* **TCP粘包拆包的处理方法**
通常使用 `自定义私有协议` 的方式来解决，协议可以按照以下方式设计：
1.	发送端发送数据时添加包头部，包头部中包含数据部分的大小，再发送数据部分；接收端先接受到包头部，确定了数据部分的大小之后再读取数据部分即可进行拆包。

2.	发送端发送数据时将数据包封装为固定长度，不够的用0补齐；接收端每一次接受固定长度的包即可进行拆包。

3.	设置消息边界，一般使用 ‘\n’ 作为边界。

<br>

<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


-----------
## TCP协议如何保证可靠传输？
1.	**连接管理**

通过三次握手与四次挥手保证能稳定的建立连接与结束连接。

2.	**序列号+确认号** 

保证对数据包的有序发送与有序接收。

3.	**校验和**

保证TCP报文段的头部与数据部分准确传输，若检验和有差错，接收端将丢弃次报文并不返回ACK报文。

4.	**超时重传机制**

发送端将缓冲区的数据发送后，并不会立刻删除缓冲区中的数据，而是收到ACK后才会删除缓冲区的数据，在等待RTO后也没有收到ACK后，将会重发数据。
>**注**：RTO（Retransmisson Time Out）是超时重传时间，一般基于RTT（Round Trip Time）时间，也就是从发送端发送数据到接收到ACK的时间。


5.	**ARQ（Auto Repeat Request）协议**

ARQ协议是数据链路层和传输层的错误纠正协议之一，分为**停止等待ARQ**，**回退n帧ARQ**，**选择重传ARQ**。

* **停止等待ARQ协议**：发送一个报文段之后，必须受到该报文段的ACK之后，才发送下一个报文段。

* **回退n帧ARQ协议**：接收窗口为1，需要从出现错误的帧开始，将之后的全部帧进行重传。


<img src="https://github.com/Worthy-Wang/offerMachine/blob/main/images/ARQ1.png">

* **选择重传ARQ**：接收窗口大于1，只需要重传错误的帧。

<img src="https://github.com/Worthy-Wang/offerMachine/blob/main/images/ARQ2.png">



6.	**设置滑动窗口进行流量控制** 

TCP发送端与接收端都有内核socket缓冲区，当接收缓冲区的剩余空间过小不能接收发送方的数据时，会提示发送方降低发送速率，从而防止丢包。

7.	**拥塞控制**

当网络出现拥塞时，应该控制发送方的发送速率，因为如果发送方没有收到ACK，会不断超时重传从而让网络更为拥挤。流量控制与拥塞控制本质上都是为了降低发送方的发送速率。

拥塞控制的四个算法：**慢开始**，**拥塞避免**，**快重传与快恢复**。

* **慢开始算法**：慢开始算法的思路是，如果刚开始在不了解网络状况的情况下，就把大量数据传输到网络中，可能会直接引起网络阻塞；那么应该从小到大增大阻塞窗口，将cwnd初始值设为1，每经过一个轮次，cwnd值增大一倍。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201029173856973.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1dvcnRoeV9XYW5n,size_16,color_FFFFFF,t_70#pic_center)
* **拥塞避免算法**：拥塞避免算法的思路是让cwnd缓慢增大，每经过一次RTT增加1。一般当拥塞窗口的值大于门限值时使用拥塞避免算法。当出现超时重传时，判断网络可能出现了拥塞，于是将门限值降为原来的一半，将cwnd值降为1并重新使用慢开始算法。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201029173907858.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1dvcnRoeV9XYW5n,size_16,color_FFFFFF,t_70#pic_center)
* **快重传算法**： 快重传算法也就是当发送方一连收到连续3个重复的ACK确认，那么相应报文段立刻重传，而不是等待超时重传。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201029173921216.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1dvcnRoeV9XYW5n,size_16,color_FFFFFF,t_70#pic_center)
* **快恢复算法**：在收到连续三次重复的ACK确认后，立刻执行快重传并进行快恢复；将 门限值 与 拥塞窗口值 均变为 原来拥塞窗口值的一半，并执行拥塞避免算法。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201029173930554.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1dvcnRoeV9XYW5n,size_16,color_FFFFFF,t_70#pic_center)
<br>

<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


---------------
## 简述UDP协议？UDP的头部结构？
我们将用户数据报协议（User Datagram Protocol）称为UDP，它是一种 **无连接**，**不可靠**，**基于数据报** 的协议。

**无连接**：数据发送方与数据接收方不需要建立对话并维持该连接。
**不可靠**：不能保证数据安全准确的传输给对方，提供“尽力而为”的交付服务。
**基于数据报**：与基于字节流不同，数据的发送与接收是有边界的。

UDP数据报**头部结构**如下：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201029180244782.png#pic_center)
UDP头部长为固定的**8字节**；

1. **第一行**
源端口号（16bit） + 目的端口号（16bit）

2. **第二行**
* **UDP总长度（16bit）**：此处的总长度为UDP 头部+数据部分 的长度，数据部分的长度受数据链路层MTU的限制，通常最大为1472字节（1500-20字节IP头部-8字节UDP头部）。
* **UDP检验和（16bit）**：当检验到错误时，UDP不做纠正，而是直接将数据丢弃。

**往下**：
数据部分（最大1472字节）

<br>

<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


----------
## TCP/UDP协议的区别
**这个问题属于一个发散性，综合性的问题，相当于让面试者详细的解释TCP协议与UDP协议。**

1.	TCP是有连接，可靠的，基于字节流的协议；UDP是无连接，不可靠，基于数据报的协议。（详细说出连接，可靠，基于字节流，基于数据报的意思，见上面的回答）

2.	TCP头部结构复杂，网络开销和时延都较大；UDP头部结构较为简单，网络开销和时延都较小。（画出TCP头部与UDP头部，并解释，见上面的回答）

3.	 TCP能通过建立连接，确认序号，滑动窗口，超时重传，拥塞控制，检验和等方式让数据包安全准确的传到对端；UDP则是提供不可靠的交付。（详细解释TCP可靠的原因，见上面的回答）

4.  TCP一般用于文件传输，收发邮件，远程登录，HTTP等，UDP一般用于即时通信，比如语音，视频，直播，DNS等。

<br>

<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


---------------
## 简述IP协议？IP协议的头部结构？
IP协议是一种**无连接**，**不可靠**的**点对点**通信协议。IP协议将不同的帧转换为统一的IP数据报的格式，使得不同技术网络，不同操作系统下的计算机也能够实现相互连通。

**无连接**：数据发送方与数据接收方不需要建立对话并维持该连接。
**不可靠**：不能保证数据安全准确的传输给对方，提供“尽力而为”的交付服务。
**点对点**：在两个网络节点之间交换数据。

<br>

**IP数据报的头部结构如下：**
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201030092415178.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1dvcnRoeV9XYW5n,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201030092426925.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1dvcnRoeV9XYW5n,size_16,color_FFFFFF,t_70#pic_center)
IP数据报头部最小为**20**个字节，最大为**60**个字节。为了方便叙述，将头部结构分为**5**行，每一行**4**字节（**32位**）。

1. **第一行**

* **版本号（4bit）**：一般是IPv4，目前IPv6仍然处于草案阶段。

* **头长度（4bit）**：一般头部长度为20个字节（0101），最大为60个字节（1111）。每一位代表4个字节，同时头部的长度也必须是4字节的整数倍（可以用充填字段充填）。

* **服务类型（8bit）**：`为不同的数据包定义不同的服务质量`，可以设置`优先级`，`最小延时`，`最大吞吐量`，最高可用性等服务，如ssh和telnet需要最小延时的服务，而文件传授ftp需要最大吞吐量的服务，另外一些紧急的数据包需要设置最高的优先级。

* **总长度（16bit）**：IP头部与数据段的总长度，每一位代表1字节，所以最大长度理论上为2^16-1 = 65535字节。当IP数据报总长度超过MTU时，就必须进行分片。

2. **第二行**

* **标识（16bit）**：当IP数据报长度超过MTU时，必须进行分片。标识字段的值就被复制到所有分片的数据报中，相同的标识字段就能够进行组装成原来的IP数据报。

* **标志（3bit）**：MF（more fragment），DF（don’t fragment）

* **片偏移（13bit）**：较大的IP数据报在分片后，该分片在原数据报中的位置。

>**通过IP数据包的分片，可以让IP分组在不同技术的网络，不同的操作系统上进行传输。**

3. **第三行**

* **TTL（8bit）**：功能是对路由器进行跳数限制，是防止无法交付的数据报在网络中兜圈子。每经过一个`路由器`，TTL减1，当TTL==0 时则丢弃该数据报；最大值可设置为255，设置为1则表示该数据报只能在本局域网中传送。

* **上层协议标识（8bit）**：区分IP协议上的上层协议，如ICMP为1，TCP为6，UDP为7。用来保证接收方知道该用哪一种协议来处理该数据报。

* **头部校验和（16bit）**：重新检验数据报的首部，但不包括数据部分。因为对数据的校验工作由`传输层协议`来完成，`网络层协议`只负责数据包在两个网络点之间进行传输。

4. **第四行**

* **源地址（32bit）**

5. **第五行**

* **目的地址（32bit）**

<br>

**可变部分（0~40字节）**


<br>


<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


------------
## 简述IP地址的组成？

>**IP地址可以在因特网中唯一的标识某一台计算机或设备。**

IP地址是一个四字节32位的数，常采用 **点分十进制** 的方式展现。编址方式：**网络号+ 主机号**，同一个物理网络上的所有主机都属于同一个网络ID，每一个主机（如工作站，服务器，路由器等）都有一个主机ID。

<br>

**IP地址的组成**：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201030103600305.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1dvcnRoeV9XYW5n,size_16,color_FFFFFF,t_70#pic_center)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201030103613545.png#pic_center)
* **A类地址**

1个字节的网络号，3个字节的主机号，用于大规模网络；
网络ID最高位必须是0，可拥有的网络数是2^7^-2个，主机数是2^24^-2个；
默认子网掩码是255.0.0.0，私网是10.0.0.0 ~ 10.255.255.255。

>**注：网络号-2的原因是0一般不用，127作为回环地址；主机号-2的原因是主机号全为0表示当前主机地址，主机号全为1表示广播地址。**

* **B类地址**

2个字节的网络号，2个字节的主机号，用于中型规模网络；
网络ID最高位必须为10，可拥有的网络数是2^14^个，主机数是2^16^-2个;
默认子网掩码是255.255.0.0，私网是172.16.0.0 ~ 172.31.255.255。

* **C类地址**

3个字节的网络号，1个字节的主机号，用于小型网络；
网络ID最高位必须是110，可拥有的网络号是2^21^个，主机号是2^8^-2个；
默认子网掩码是255.255.255.0，私网是192.168.0.0~192.168.255.255。

* **D类地址**

D类地址称为广播地址也可以称为多播，组播地址；
网络ID开头必须为1110，范围为223.0.0.0~239.255.255.255；
每个地址对应着一个组，发往某一组播地址的数据将被该组中所有成员接收。

>**D类地址不能够	分配给主机。**

* **E类地址**

E类地址作为保留地址之后使用。


* **特殊地址**

特殊地址也就是专用的地址，**不能够分配给主机使用**：

1. **0.0.0.0**
并不是一个真实的地址，对应着当前网络所有的IP地址。
	
1. **回环地址**
以127开头的地址称为回环地址，给回环地址发送的IP数据报都会被主机接收，外部设备也无法通过回环地址访问该主机；回环地址通常用来测试某台机器的网络设备是否正常。

2. **主机地址全为0**
对应着当前的网络地址

3. **主机地址每个字节都为1**
对应着该网络的广播地址



<br>


<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


-------------
## 0.0.0.0	与 127.0.0.1 与 localhost的区别?
* **127.0.0.1**
实际上从127.0.0.1~127.255.255.254都属于回环地址，都能够ping通，只是我们默认在回环地址中使用127.0.0.1进行测试。

* **localhost**
 实际上经过DNS域名解析后的localhost就是127.0.0.1，就像www.baidu.com（域名，或者说别名）对应着它自己的IP地址一样。

* **0.0.0.0**
并不是一个真实的地址，对应着当前网络所有的IP地址。

举例说明：
PC1 和 PC2 在同一个局域网中，PC1的地址是172.21.0.7
1.	PC1作为server监听172.21.0.7，PC1中的client只能够连接上172.21.0.7，PC2的client只能连接上172.21.0.7
2.	PC1作为server监听127.0.0.1，PC1中的client只能连接上127.0.0.1，PC2中的client都连接不上。
3.	PC1作为server监听0.0.0.0，PC1中的client两个都能连接上，PC2中的client可以连接上172.21.0.7

<br>


<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


-------------
## NAT协议的作用？（公网与私网的区别？）

**NAT协议的作用实现公网IP地址与私网IP地址之间的相互映射转换，使得一个公网IP地址下能够有多个私网IP。**
**作用**：
1. 解决了IPv4地址枯竭的问题；
2. 主机的安全性得到了保障，因为就算暴露了私网IP也没有关系。

我们的家庭网络，以及寝室都是采用的这种NAT协议。

**举例**：
>我寝室里面的主机（公网IP为125.1.2.3，私网IP为10.1.0.2）向Web服务器（公网IP为162.105.129.12）请求服务。由内网到外网时，将源IP地址从10.1.0.2改为125.1.2.3，从外网到内网时，将目的IP地址从125.1.2.3改为10.1.0.2，由NAT路由器进行路由表映射操作完成。
NAT路由表如下：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201030103824430.png#pic_center)

<br>

<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>


--------------
## ARP协议是什么？
**ARP协议（Address Resolution Protocol）的作用是实现从IP地址到MAC地址的映射。**

主机发送信息时将包含 **目标IP地址** 的 **ARP请求** 在 **局域网** 进行 **广播**，并根据返回的消息确定 **目标IP地址** 的 **MAC地址**，以 	**<IP，MAC>** 形式存入 **ARP缓存表**。



>**举例：ARP协议工作过程**
主机A  IP:192.168.0.1  MAC: 0A-11-22-33-44-01
主机B  IP:192.168.0.2  MAC: 0A-11-22-33-44-02
>1.	A在路由表中找到主机B的IP地址是192.168.0.2。
>2.	A在ARP缓存表中查找B的IP映射MAC地址，发现没有找到，于是在局域网内进行广播，发出的帧包含A的IP地址以及MAC地址。
>3.	除B以外的主机接收到帧后，发现目标地址与自己的地址并不匹配，于是将帧丢弃；主机B接收到帧后，将主机A的<IP，MAC>信息存入自己的ARP缓存表，并发送回应消息。
>4.	A接收到消息，将B的<IP，MAC>信息存入ARP缓存表。
>5.	A将IP数据报装帧，发送给B。

**注意**：ARP请求只能在局域网中进行，且ARP协议并不会验明其真实性就记入ARP缓存，所以发送的信息可能会到达错误的主机，形成ARP欺骗。

<br>

<div align="right">
    <b><a href="#目录">↥ Back To Top</a></b>
</div>

