# include指令

Include指令用于在编译阶段包括一个文件。这个指令告诉容器在编译阶段将其他外部文件的内容合并到当前JSP文件中。可在JSP页面的任何位置使用include指令进行编码。
本指令的一般用法形式如下：
<%@ include file = "relative url" %>

include指令中的文件名实际上是一个相对URL。如果只指定一个没有关联路径的文件名，那么JSP编译器会假定该文件与JSP在同一个目录中。可以使用XML编写上述代码效果相同，如下所示：

```jsp
<jsp:directive.include file = "relative url" />
```

include指令的一个很好的例子是要一个页面中包括多个公共页面的内容，如：比如一个主页中包函公共页眉和页脚。