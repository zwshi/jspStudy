# plugin动作

&#60;jsp:plugin&#62;动作可以在页面中插入 Java Applet 小程序或 JavaBean，它们能够在客户端运行，但此时，需要在 IE 浏览器中安装 Java 插件。当 JSP 文件被编译并送往浏览器时，&#60;jsp:plugin&#62; 动作将会根据浏览器的版本，替换成 &#60;object> 或者&#60;embed&#62; 页面 HTML 兀素。

注意，&#60;object&#62; 用于 HTML 4.0，&#60;embed&#62; 用于 HTML 3.2。

通常，<jsp:plugin> 元素会指定对象是 Applet 还是 Bean，同样也会指定 class 的名字以及位置。另外，还会指定将从哪里下载 Java 插件。该动作的语法格式如下：

<jsp:plugin
type="bean|applet" code="ClassFi1eName"
codebase="classFileDirectoryName"
[name="instanceName"]
[archive="URIToArchive,..."]
[align="bottom|top|middle|left|right"]
[height="displayPixels"]
[width="displayPixels"]
[hspace="leftRightPixels"]
[vspace="topBottomPixels"]
[jreversion="JREVersionNumber|1.1"]
[nspluginurl="URLToPlugin"]
[iepluginurl="URLToPlugin"] >
[<jsp:params>
<jsp:param name="parameterName"
value="{parameterValue|<%=expression %>" />
</jsp:params>]
[<jsp:fallback>text message for user</jsp:fallback>]
</jsp:plugin>

参数说明如下：

    type 属性的作用是定义插入对象的类型，对象类型有两个值，分别是 bean 或者 applet。（必须定义的属性）
    code 属性定义插入对象的类名，该类必须保存在 codebase 属性指定的目录内。（必须定义的属性）
    codebase 属性定义对象的保存目录。（必须定义的属性）
    name 属性定义 bean 或 Applet 的名字。
    archive 属性定义 Applet 运行时需要的类包文件。
    align 属性定义 Applet 的显示方式。
    height 属性定义 Applet 的高度。
    width 属性定义 Applet 的长度。
    hspace 属性定义 Applet 的水平空间。
    vspace 属性定义 Applet 的垂直空间。
    jreversion 属性定义 Applet 运行时所需要的 JRE 版本，缺省值是 1.1。
    nspluginurl 属性定义 Netscape Navigator 用户在没有定义 JRE 运行环境时下载 JRE 的地址。
    iepluginurl 属性定义 IE 用户在没有定义 JRE 运行环境时下载 JRE 的地址。
    jsp:params 标识的作用是定义 Applet 的传入参数。
    jsp:fallback 标识的作用是当对象不能正确显示时传给用户的信息。
