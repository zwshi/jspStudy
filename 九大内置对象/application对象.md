# application对象

实现了用户间数据的共享，可存放全局变量
开始于服务器的启动，终止于服务器的关闭
在用户的前后连接或不同用户之间的连接中，可以对application对象的同一属性进行操作

例:

```html
<body>
  <h1>appliction内置对象</h1>
    <%
        application.setAttribute("username","zwish");
        application.setAttribute("sex","male");
        application.setAttribute("work","student");
    %>
    姓名:<%=application.getAttribute("username") %><br>
    application中的属性有:
    <%
        Enumeration attributes = application.getAttributeNames();
        while(attributes.hasMoreElements()){
            out.println(attributes.nextElement()+"&nbsp;&nbsp;");
        }
    %><br>
    Jsp(Servlet)引擎名及版本号:<%=application.getServerInfo() %>
  </body>
```