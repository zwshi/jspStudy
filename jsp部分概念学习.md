# 上机总结

1、
(1)表达式：
    <%=比到时 %>
(2)脚本:
    <% 代码片段 %>
(3)注释:
    <%--jsp注释 --%>
    <!--html注释-->
    //java注释
(4)声明:
    <%! >  可以定义一些变量，也可以定义一些方法供后面使用

(5)jsp指令：
    <%@ page.... %>
    <%@ include.... %>
    <%@ taglib.... %>

<%@ page 属性1="属性值" 属性2="属性值">
    language：
    contenType：
    import:

2、jsp里处理http请求和servelt一样，只不过要在<% %>里写代码
    例：

    ```jsp
    <%
        //这里将用户名取出来，然后附加到session上
            String name=request.getParameter("username");
            out.println("用户名:"+name);
            HttpSession s=request.getSession();
            s.setAttribute("name",name);

        %>
    ```

    Session在servlet里是一个对象，只要没超过设置的最大存留时间和关闭浏览器，则会一直存在，并且在不同页面都可以使用

3、jsp中include的两种用法：
    include指令，是在JSP文件被转换成Servlet的时候引入文件，而jsp:include动作不同，插入文件的时间是在页面被请求的时候。

4、请求重定向与请求转发
请求重定向：客户端行为，response.sendRedirect(),从本质上讲等于两次请求，前一次的请求对象不会保存，地址栏的URL地址会改变
请求转发:服务器行为，request.getRequestDispatcher().forward(request,response);是同一次请求，转发后请求对象会保存，地址栏的URL地址不会变