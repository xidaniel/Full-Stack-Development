# Tomcat

---

是什么?

管理(调度)servlet的**web容器**,用来启动或者结束相应的servlet.向servelet提供http请求和响应. 
servlet可以看作服务器端处理数据的java小程序,但是servlet没有main方法,无法自己启动.

---

作用:

```markdown
1. 通信支持:实现servlet和web服务器的对话
2. 生命周期管理:加载,实例化,初始化,调用,回收等.
3. 多线程支持:管理多个线程
4. 声明式安全: 可以用xml文件部署描述文件来配置安全性
5. jsp支持: 将jsp翻译成java
```

---

Tomcat 目录结构:

```markdown
📁bin       存放Tomcat的可执行程序, starup.bar
📁conf      存放Tomcat服务器的配置文件
📁lib       存放的jar包
📁logs      存放服务器运行时输出的日记信息
📁temp      存放运行时产生的临时数据
📁webapps   存放部属的一些web工程,一个目录一个工程
📁work      工作时的目录,存放Tomcat运行时jap翻译为servlet的源码,和session序列化目录
```

---

MAC OS 安装:

```markdown
brew install tomcat

Using Tomcat:
 	1. start: catalina start
      	1. test: http://localhost:8080; http://127.0.0.1:8080;
	2. stop: catelina stop
```

---

修改端口号

```markdown
1. 📁conf --> server.xml --> Connect prot="8080"
2. restart Tomcat

Notice: prot 80 是http的默认端口号,不会在url中显示
```

---

如何部署

```java
1. 📁webapps   直接拷贝到webapps目录下
2. 访问:      http://localhost:8080/具体文件地址
```

```java
1. 📁conf --> Cataline --> localhost
2. 创建xml配置文件
  1. <Context path="/xml.文件名" docBase="项目文件地址" />
```

---

ROOT工程

```markdown
http://ip:port/   没有工程名 -->访问ROOT工程
http://ip:port/工程名/   没有资源名 --> 访问ROOT工程 就是index文件
```

