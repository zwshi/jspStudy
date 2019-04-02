# getProperty动作

<jsp:getProperty> 标记用来获得 bean 中的属性，并将其转换为字符串，再在 JSP 页面中输出，该 bean 中必须具有 getXxx() 方法。使用的语法格式如下：

<jsp:getProperty name="Bean 实例名" property="prbpertyName" />

下面对 name 属性和 property 属性的用法进行详细介绍。

(1) name 属性：用来指定一个存在于 JSP 中某个范围内的 bean 实例。

<jsp:getProperty> 标记会按照 page、request、session 和 application 的顺序查找 bean 实例，直到第一个实例被找到。如果任何范围内都不存在这个 bean 实例，则会拋出异常。

(2) property 属性：该属性指定要获取由 name 属性指定的 bean 中的哪个属性的值。若它指定的值为 stuName，那么 bean 中必须存在 getStuName() 方法，否则会拋出异常。如果指定 bean 中的属性是一个对象，那么该对象的 toString() 方法将被调用，并输出执行结果。