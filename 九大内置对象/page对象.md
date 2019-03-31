# page

与类的 this 指针类似，使用它来调用 Servlet 类中所定义的方法，只有在本页面内才是合法的。它是 java.lang.Object 类的实例
方法有：
page.getClass()
page.hashCode()
page.toString()
page.equals()

```jsp
<%@ page contentType="text/html;charset=utf-8" import="java.lang.Object" %>
<html>
    <body>
        <h2> page对象应用</h2>
        <%
        Object obj;
        obj=null;
        %>
        返回当前页面所在类：<%=page.getClass()%> <br>
        返回当前页面的 hash 代码：<%=page.hashCode()%> <br>
        转换成 String 类的对象：<%=page.toString()%> <br>
        比较1：<%=page.equals(obj) %> <br>
        比较2：<%=page.equals(this) %>
    </body>
</html>
```