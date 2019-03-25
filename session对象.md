# session

session是jsp的内置对象
常用方法有：

```jsp
<%
    session.getId();
    session.getCreationTime();
    session.setAttribute();
    session.getAttribute();
    session.setMaxInactiveInterval(10);
    session.getValueNames();
%>
```