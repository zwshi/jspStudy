# 四大范围

```jsp
范围1(page)内的值：<%=pageContext.getAttribute("info",1) %> <br>
范围2(request)内的值：<%=pageContext.getAttribute("info",2) %> <br>
范围3(session)内的值：<%=pageContext.getAttribute("info",3) %> <br>
范围4(application)内的值：<%=pageContext.getAttribute("info",4) %> <hr>
```