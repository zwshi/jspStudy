# 对象

1、out 对象
JspWriter类的实例

```jsp
<%
    out.println("<h2>my name is zwish<h2>")

%>
缓冲区大小:<%=out.getBufferSize()%> byte<br>
缓冲区剩余大小:<%=out.getRemaining() %> byte<br>
是否自动清空缓冲区:<%=out.isAutoFlush() %>
```

2、request对象：

```html
<html>
    <body>
    <form action="dologin.jsp" method="post">
        <table>
            <tr>
            <td>用户：</td>
            <td><input type="text" name="username"></td>
            </tr>
            <tr>
            <td>hobby：</td>
            <td>
                <input type="checkbox" name="favorite" value="read">阅读
                <input type="checkbox" name="favorite" value="music">音乐
                <input type="checkbox" name="favorite" value="football">足球
            </td>
            </tr>
        </table>
    </form>

    <br>
    <a href="dologin.jsp?username=张三">测试URL传参数</a>
    </body>
</html>
```

```jsp
//dologin.jsp
<%
    request.setCharacterEncoding("提交表单时的字符集");//当显示中文为乱码时，但无法解决url传参时传中文显示乱码的问题（这里需要修改tomcat服务器的service.xml,在connector标签里添加URIEncoding="utf-8"）
    request.setAttribute("password","123456");
%>
用户名：<%=request.getParameter("username") %><br>
爱好:<%
if(request.getParameterValues("favorites")!=null)
{
    String[] favorites = request.getParameterValues("favorite");
    for(int i=0;i<favorites.length;i++){
        out.println(favorites[i]+"&nbsp;&nbsp;");
    }
}
密码:<%=request.getAttribute("password")%>
请求体的MIME类型:<%=request.getContentType()%>
协议类型及其版本号:<%=request.getProtocol()%>
服务器名:<%=request.getServerName()%>
服务器的端口号:<%=request.getServerPort()%>
请求文件的长度:<%=request.getContentLength()%>
请求的真实路径:<%=request.getRealPath()%>
请求的上下文路径:<%=request.getContextPath()%>

%>
```

3、response对象

```jsp
<%response.setContentType("text/html;charset=utf-8");%>
<%
PrintWriter outer=response.getWriter();
outer.println("response对象使用PrintWriter创建的对象，与内置对象out不同,打印的类容输出在内置out对象的前面");
out.println("内置对象out");

response.sendRedirect("reg.jsp");//请求重定向
%>
```