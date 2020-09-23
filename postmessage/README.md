# 介绍如何使用postmessage给不同域的页面传消息

# 说明 

## 目录 a/a.html

本机使用http-server 启动a.html，地址为： http://192.168.1.17:8082/a.html


## 目录 b/b.html

本机使用http-server 启动b.html，地址为： http://192.168.1.17:8083/b.html


## 验证

a.html页面上的交互完成后，单独在浏览器打开b.html，可以看到b.html的localStorage里值会发生变化。说明成功。
