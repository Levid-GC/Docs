# Tomcat

## 安装

### Windows

解压后，双击 `bin/startup.bat` 即可启动。如遇中文乱码，将 `conf/logging.properties` 中 `UTF-8` 全部更改为 `GB2312`。

### Linux

## 原理

### Container 内部组件关系示例

在默认的配置下，`webapps` 目录下，每一个目录代表一个应用，而 `ROOT` 代表主应用，而整个 `webapps` 就是一个站点。举个例子：`www.imooc.com` 这个网站就代表一个站点，对应的就是 `webapps` 这个目录，而 `ROOT` 这个主应用就可以直接使用域名去访问。如果 `webapps` 下有一个 `test` 目录，就可以使用 `www.imooc.com/test` 去访问。而 `class.imooc.com` 则属于另外一个站点，也就是属于另外一个 Host。

### Server 处理 HTTP 请求

1. 用户点击网页，请求被发送到本机端口的 8080，被监听 8080 的 Connector 获得。
2. Connector 将请求交给 Server 的 Engine 处理，等待 Engine 的回应。
3. Engine 获得到的请求是：`http://localhost/test/index.jsp`，匹配所有的虚拟主机，也就是 `localhost` 的 Host。
4. Host 使用 `test/index.jsp` 匹配 Context。
5. Context 使用 `index.jsp` 匹配 Servlet。
6. Servlet 处理请求，并原路返回。
