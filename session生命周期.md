# session生命周期

session销毁的三种方式
1、session.invalidate()方法
2、session过期（超时）默认超时时间为30分钟，
可以使用session.setMaxInactiveInterval()设置，
也可以在web.xml中设置:

```xml
<session-config>
<session-timeout>10</session-timeout>
</session-config>
```

3、服务器重新启动