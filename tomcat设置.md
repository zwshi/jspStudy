# 修改tomcat默认端口

将下面的port改为其他的值

```xml
    <Connector port="8080" protocol="HTTP/1.1"
               connectionTimeout="20000"
               redirectPort="8443" />
```