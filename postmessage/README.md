# 介绍如何使用postmessage给不同域的页面传消息

# 说明 

## 目录 a/a.html

本机使用http-server 启动a.html，地址为： http://192.168.1.17:8082/a.html


## 目录 b/b.html

本机使用http-server 启动b.html，地址为： http://192.168.1.17:8083/b.html


## 验证

## 文章摘引
a.html页面上的交互完成后，单独在浏览器打开b.html，可以看到b.html的localStorage里值会发生变化。说明成功。

4、使用HTML5中新引进的window.postMessage方法来跨域传送数据

window.postMessage(message,targetOrigin)  方法是html5新引进的特性，可以使用它来向其它的window对象发送消息，无论这个window对象是属于同源或不同源，目前IE8+、FireFox、Chrome、Opera等浏览器都已经支持window.postMessage方法。

调用postMessage方法的window对象是指要接收消息的那一个window对象，该方法的第一个参数message为要发送的消息，类型只能为字符串；第二个参数targetOrigin用来限定接收消息的那个window对象所在的域，如果不想限定域，可以使用通配符 *  。

需要接收消息的window对象，可是通过监听自身的message事件来获取传过来的消息，消息内容储存在该事件对象的data属性中。

上面所说的向其他window对象发送消息，其实就是指一个页面有几个框架的那种情况，因为每一个框架都有一个window对象。在讨论第二种方法的时候，我们说过，不同域的框架间是可以获取到对方的window对象的，而且也可以使用window.postMessage这个方法。下面看一个简单的示例，有两个页面