## 为什么会产生AJAX跨域？

1. 浏览器限制
2. 跨域
3. XHR请求


## jsonp的弊端

1. 服务器需要改动代码
2. 只支持GET
3. 发送的不是XHR请求，XHR支持异步等特性


## 被调用方解决 在响应头增加字段

1. *服务端实现*

2. nginx配置

3. apache配置


## 简单请求和非简单请求

工作中比较常见的简单请求：

请求方法：

1. get
2. head
3. post

请求header里面：

1. 没有自定义头
2. Content-Type为：text/plain multipart/form-data application/x-www-form-urlencodeed


工作中常见的非简单请求有：

1. 请求方法为put
2. 请求方法为delete
3. 发送json格式的ajax请求
4. 带自定义头的ajax请求



非简单请求在发送请求的时候会发送一个预检的请求(OPTIONS)

预检命令的缓存：

```java
 response.addHeader("Access-Control-Max-Age","3600");// 单位秒。告诉浏览器，在指定时间内，缓存设置的以上信息，不需要发送options请求
```
但是如果浏览器控制台勾选了Disable Cache 那么，也会发送options命令。


## 发送带cookie的请求

1. Access-Control-Allow-Origin 必须是全匹配，不能使用*
2. Access-Control-Allow-Credentials 设置为true
