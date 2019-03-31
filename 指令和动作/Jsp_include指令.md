# include指令

JSP include 指令用于通知 JSP 引擎在翻译当前 JSP 页面时，将其他文件中的内容合并进当前 JSP 页面转换成的 Servlet 源文件中，这种在源文件级别进行引入的方式，称为静态引入
当前 JSP 页面与静态引入的文件紧密结合为一个 Servlet。这些文件可以是 JSP 页面、HTML 页面、文本文件或是一段 Java 代码。其语法格式如下：

<%@ include file="relativeURL|absoluteURL" %>

使用 include 指令是以静态方式包含文件，也就是说，被包含文件将原封不动地插入 JSI 文件中，因此，在所包含的文件中不能使用 <html></html>、<body></body> 标记，否则会因为与原有的 JSP 文件有相同标记而产生错误。
另外，因为原文件和被包含文件可以相互访问彼此定义的变量和方法，所以要避免变量和方法在命名上产生冲突。

```jsp
<%@ page language="java" import="java.util.*,java.text.SimpleDateFormat" contentType="text/html; charset=utf-8"%>
  <!-- 本页面显示时间 -->
    <%
    Date d=new Date();
    SimpleDateFormat sdf = new SimpleDateFormat("yyyy年MM月dd日HH时mm分ss秒");
    out.println(sdf.format(d));
    %>
```

```jsp
<body>
   <h1>include指令</h1>
   <hr>
   <%@ include file="Date.jsp" %>
  </body>
```