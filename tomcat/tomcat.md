1.  什么是HTTP？
    http协议的本质是一种浏览器与服务器之间约定好的通讯格式
3.  什么是servlet接口？ 为什么需要servlet容器？
    servlet接口其实是servlet容器跟具体业务之间的接口。servlet接口定义了5个方法分别是：init、getServletConfig、service、getServletInfo和destroy。其中最终要的是service，具体业务类在这个方法里实现处理逻辑。
4.  servlet的容器主要作用是什么？
    