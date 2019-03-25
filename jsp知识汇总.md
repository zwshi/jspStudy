# jsp

常用动态网络开发技术对比：
jsp：java平台，安全性高，适合开发大型的、企业级的web应用程序
Asp.net：net平台，简单易学，但是安全性和跨平台性差
php：简单高效，成本低开发周期短，适合中小企业，Lamp：Linux+Apache+mysql+php）

jsp页面组成部分：静态内容、指令、表达式、小脚本、声明、注释

1、脚本程序：可以包含任意量的Java语句、变量、方法或表达式，只要它们在脚本语言中是有效的。
脚本程序的语法格式：<% 代码片段 %>
也可以编写与其等价的XML语句，就像下面这样：
<jsp:scriptlet>
   代码片段
</jsp:scriptlet>

2、JSP声明
一个声明语句可以声明一个或多个变量、方法，供后面的Java代码使用。在JSP文件中，您必须先声明这些变量和方法然后才能使用它们。
JSP声明的语法格式：

<%! declaration; [ declaration; ]+ ... %>

3、JSP表达式
一个JSP表达式中包含的脚本语言表达式，先被转化成String，然后插入到表达式出现的地方。
由于表达式的值会被转化成String，所以您可以在一个文本行中使用表达式而不用去管它是否是HTML标签。
表达式元素中可以包含任何符合Java语言规范的表达式，但是不能使用分号来结束表达式。
JSP表达式的语法格式：
<%= 表达式 %>

4、JSP指令
JSP指令用来设置与整个JSP页面相关的属性。
JSP指令语法格式：
    <%@ directive attribute="value" %>
这里有三种指令标签：
    <%@ page ... %>   定义页面的依赖属性，比如脚本语言、error页面、缓存需求等等
    <%@ include ... %>   包含其他文件
    <%@ taglib ... %>  引入标签库的定义，可以是自定义标签

注：
include指令的一个很好的例子是要一个页面中包括多个公共页面的内容，如：比如一个主页中包函公共页眉和页脚。
可以根据您的应用功能来设计网页; 建议将网站的动态部分保存在单独的文件中，然后将其包含在主文件中。当需要更改网页的一部分时，只需要修改少数几个地方就可以轻松实现。

 当用户第一次请求一个jsp页面时，首先被执行的方法是构造方法

 #########jsp内置对象
 web容器创建的一组对象，不使用new就可以使用的内置对象
 比如out对象，out.println()
 jsp九大内置对象：out、request、response、session、application、page、pagecontent、exception、config

5.JSP动作
JSP动作使用XML语法中的结构来控制的servlet引擎的行为。可以动态插入文件，重新使用的JavaBeans组件，将用户转发到另一个页面，或为Java的插件生成HTML。
只有一个用于动作元素语法，因为它符合XML标准
<jsp:action_name attribute="value" />
XML
动作元素基本上是预定义的功能，下表列出了可用的JSP动作

jsp:include
在请求页面时包含一个文件。

jsp:useBean
查找或实例化一个JavaBean的。

jsp:setProperty
设置JavaBean的属性的值。

jsp:getProperty
将JavaBean的属性的值输出。

jsp:forward
将请求者转发到新页面。

jsp:plugin
生成针对Java的创建³³插件OBJECT或EMBED标记的特定于浏览器的代码。

jsp:element
动态定义XML元素。

jsp:attribute
定义动态定义的XML元素属性。

jsp:body
定义动态定义的XML元素的正文。

jsp:text
用于在JSP页面和文档中编写模板文本。
