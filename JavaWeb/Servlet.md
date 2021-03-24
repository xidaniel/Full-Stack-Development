# Servlet

---

**是什么?**

1. 是Java中的interface
2. JavaWeb三大组件之一. (servlet, filter, listener)
3. 运行在Web服务器中的小型Java程序. servlet通常通过HTTP**接受和响应来自Web客户端的请求,并响应数据给客户端**.

---

**应用Servlet**

- 🏁实际项目开发中都是使用**HttpServlet class**的方式去实现Servlet,**可以用IDEA快速生成**

URL定位servlet的request以及response

```markdown
前端button按钮: <from action= "http://localhost:8080/servlet_project/hello" method="get">

1. protocal: http://
2. 根据ip地址定位服务器: localhost
3. 与服务器prot通信: 8080
		1. find Tomcat
		2. Tomcat 找到工程文件 servlet_project
		3. 先去 web.xml 中找到对应的servlet-name
		4. 调用 servlet-class
		5. 通过req.getMethod()得到前端是使用get方法还是post方法
		6. 根据业务的需要重写**doGet()**和**doPost()**的方法
		7. 返回给前端页面
```

---

Servlet生命周期

```markdown
1. 执行 servlet constructor
2. 执行 init method
   // 1和2 同时执行
3. 执行 service method
   //每次页面刷新都会调用
4. 执行 destroy method
   // web工程停止时候销毁
```

---

其他servlet class

servletConfig

servletContext: 一个工程只会创建一个object

---

**例子**用servlet interface实现:

	1. 主要是实现**service**方法, 处理请求, 并响应数据
 	2. 到web.xml中配置servlet程序的访问地址

```java
import javax.servlet.*;
import java.io.IOException;

public class HelloServlet implements Servlet {
    @Override
    public void init(ServletConfig servletConfig) throws ServletException {
				System.out.println("Init Servlet!");
    }

    @Override
    public ServletConfig getServletConfig() {
        return null;
    }

    /*
    service 专门用来处理请求和相应的
     */
    @Override
    public void service(ServletRequest servletRequest, ServletResponse servletResponse) throws ServletException, IOException {
        System.out.println("Hello Servlet!");
    }

    @Override
    public String getServletInfo() {
        return null;
    }

    @Override
    public void destroy() {
				System.out.println("destory Servlet!");
    }
}
```

```xml
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns="http://xmlns.jcp.org/xml/ns/javaee"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee http://xmlns.jcp.org/xml/ns/javaee/web-app_4_0.xsd"
         version="4.0">

    <!--给tomcat配置servlet程序-->
    <servlet>
        <!--给servlet程序取一个别名-->
        <servlet-name>HelloServlet</servlet-name>
        <!--servlet-class 是servlet程序全类名 -->
        <servlet-class>com.xi.servlet.HelloServlet</servlet-class>
    </servlet>


    <!-- servlet-mapping给servlet配置访问地址-->
    <servlet-mapping>
        <!-- 告诉服务器， 当前配置的地址给那个servlet程序使用-->
        <servlet-name>HelloServlet</servlet-name>
        <!-- 配置访问地址为： http://ip:prot/工程目录/hello -->
        <url-pattern>/hello</url-pattern>
    </servlet-mapping>
</web-app>

```



