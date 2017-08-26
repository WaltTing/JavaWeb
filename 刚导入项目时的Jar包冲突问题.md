刚导入项目时，各种报错，经度娘，最终得出的结论就是：

> 项目中的jar包和tomcat的jar包发生了冲突。

具体的错误是出现了诸如Servlet.service() for servlet jsp threw exception这样的问题。
最终的解决方案是：

> 将项目中的jar包替换成tomcat中的jar包。

- jsp-api.jar
- el-api.jar
- jasper.jar
- jasper-el.jar
- servlet-api.jar