# Page指令

JSP中的page指令用于向容器提供与当前JSP页面相关的指令。可以在JSP页面的任何位置使用page指令进行编码。 按照惯例，page指令被编码在JSP页面的顶部。

jsp基础语法：

```jsp
<%@ page attribute = "Value" %>
```

也可以使用XML编写上述语法：

```xml
<jsp:directive.page attribute = "Value" />
```

序号|属性|说明
:---:|:---:|:---:
1|buffer|指定输出流的缓冲模型。
2|autoFlush|控制servlet输出缓冲区的行为。
3|contenType|定义字符编码方案。
4|errorPage|定义另一个报告Java未检查运行时异常的JSP的URL。

上面的表格没写完，具体的可以看下面的

1.buffer属性buffer属性指定服务器输出响应对象的缓冲特性。
可以编写指一个none值来指定不使用缓冲，以便servlet输出立即被定向到响应对象，或者可以编写一个以KB为单位的最大缓冲区大小，这将指示servlet在写入响应之前写入缓冲区。
如要指示servlet将输出直接写入响应输出对象，请使用以下命令 -

```jsp
<%@ page buffer = "none" %>
```

使用以下命令来指示servlet将输出写入大小不小于64KB字节的缓冲区 -

```jsp
<%@ page buffer = "64kb" %>
```

2.autoFlush属性autoFlush属性指定缓冲区输出是否在缓冲区填充时自动刷新，或者是否引发异常以指示缓冲区溢出。
true(默认值)值表示自动缓冲区刷新，false值表示引发异常。
当servlet的输出缓冲区已满时，以下指令会导致servlet抛出异常，则使用以下语句 -

```jsp
<%@ page autoFlush = "false" %>
```

此指令使servlet在完全输出时刷新输出缓冲区，

```jsp
<%@ page autoFlush = "true" %>
```

通常，buffer和autoFlush属性在page指令中进行编码，如下所示：

```jsp
<%@ page buffer = "16kb" autoflush = "true" %>
```

3.contentType属性contentType属性设置JSP页面和生成的响应页面的字符编码。 默认内容类型为：text/html，它是HTML页面的标准内容类型。
如果要从JSP输出为XML，请使用以下page指令 -

```jsp
<%@ page contentType = "text/xml" %>
```

以下语句指示向浏览器生成的页面呈现为HTML -

```jsp
<%@ page contentType = "text/html" %>
```

以下指令将内容类型设置为：Microsoft Word文档 -

```jsp
<%@ page contentType = "application/msword" %>
```

还可以指定响应的字符编码。 例如，如果要指定返回浏览器的结果页面使用：UTF-8，则可以使用以下page指令 -

```jsp
<%@ page contentType = "text/html:charset=UTF-8" %>
```

4.errorPage属性如果希望在当前页面运行时出现错误时，指定一个错误提示页面，那么errorPage属性告诉JSP引擎显示哪个页面。errorPage属性的值是相对URL。
当抛出所有未捕获的异常时，以下指令用于在页面出错时指定显示MyErrorPage.jsp的内容 -

```jsp
<%@ page errorPage = "MyErrorPage.jsp" %>
```

5.isErrorPage属性isErrorPage属性表示当前的JSP页面可以用作另一个JSP的错误页面。
isErrorPage的值可为true或false。 isErrorPage属性的默认值为false。
例如，handleError.jsp将isErrorPage选项设置为true，因为它应该处理错误 -

```jsp
<%@ page isErrorPage = "true" %>
```

6.extends属性extends属性指定生成的servlet必须扩展的超类。
例如，以下指令指示JSP转换器生成servlet，以使servlet扩展somePackage.SomeClass -

```jsp
<%@ page extends = "somePackage.SomeClass" %>
```

7.import属性import属性与Java import语句具有相同的功能，并且类似于Java import语句。import选项的值是要导入的程序包的名称。
例如，要导入java.sql.*，请使用以下page指令 -

```jsp
<%@ page import = "java.sql.*" %>
```

要导入多个包，可以使用逗号分隔，如下所示：

```jsp
<%@ page import = "java.sql.*,java.util.*"  %>
```

默认情况下，容器会自动导入java.lang.\*，javax.servlet.\*，javax.servlet.jsp.\*和javax.servlet.http.\*。
8.info属性info属性允许提供JSP的描述。以下是一个代码示例 -

```jsp
<%@ page info = "This JSP Page Written By Maxsu"  %>
```

9.isThreadSafe属性isThreadSafe选项将页面标记为线程安全。默认情况下，所有JSP都被认为是线程安全的。 如果将isThreadSafe选项设置为false，则JSP引擎确保一次只有一个线程正在执行JSP。
以下page指令将isThreadSafe选项的值设置为false -

```jsp
<%@ page isThreadSafe = "false"  %>
```

10.language属性language属性指示在JSP页面脚本编写中使用的编程语言。
例如，由于通常我们使用Java作为脚本语言，因此language选项可设置成如下：

```jsp
<%@ page language = "java" %>
```

11.session属性session属性指示JSP页面是否使用HTTP会话。如果设置值为true，则表示JSP页面可以访问内置session对象，设置值为false表示JSP页面无法访问内置session对象。
以下指令允许JSP页面使用任何内置session对象方法，如：session.getCreationTime()或session.getLastAccessTime()

```jsp
<%@ page session = "true" %>
```

12.isELIgnored属性isELIgnored属性能够禁用JSP 2.0中引入的表达式语言(EL)表达式的求值计算。
isELIgnored属性的默认值为true，这意味着表达式${...}按JSP规范进行评估计算。如果属性设置为false，则不会对表达式进行评估求值，而将其视为静态文本内容。
以下指令设定表达式不会被评估计算 -

```jsp
<%@ page isELIgnored = "false" %>
```

13.isScriptingEnabled属性isScriptingEnabled属性确定脚本元素是否被允许使用。
isScriptingEnabled属性默认值为true，它表示启用脚本，表达式和声明。 如果属性的值设置为false，则如果JSP使用任何脚本，表达式(非EL)或声明，则会引发转换时错误。
如果要限制脚本，表达式(非EL)或声明的使用，可将isScriptingEnabled属性的值可以设置为false

```jsp
<%@ page isScriptingEnabled = "false" %>
```