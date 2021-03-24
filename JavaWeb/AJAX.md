# AJAX

---

**是什么?**

1. Asynchronous Javascript And XML
2. 通过js异步发起请求,**局部更新页面的技术.**
3. AjaxServlet extends BaseServlet

---

**特点**

1. 局部更新,原来的页面不会发生变化
2. synchronous的用户体验很差, Asynchronous推荐
   1. synchronous --> 只有当这个完成时候才能进行下一个
   2. Asynchronous --> 页面交互功能之间不受影响

---

**使用**

用framework中的AJAX请求

.ajax方法

	-	url: 表示请求的地址
	-	type: 表示请求的类型GET或POST请求
	-	data: 表示发送给服务器的数据
	-	success: 请求响应,响应的回调函数
	-	dataType: 响应的数据类型

