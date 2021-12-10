1.  什么是HTTP？
    http协议的本质是一种浏览器与服务器之间约定好的通讯格式
2.  什么是servlet接口？ 为什么需要servlet容器？
    servlet接口其实是servlet容器跟具体业务之间的接口。servlet接口定义了5个方法分别是：init、getServletConfig、service、getServletInfo和destroy。其中最终要的是service，具体业务类在这个方法里实现处理逻辑。
3.  servlet的容器主要作用是什么？
    servlet容器主要作用是IO流转换处理（客户端请求解析将HttpRequest转换成servletRequest，然后交给servlet处理，servlet处理完的结果servletResponse转换成httpResponse），和servlet的管理。tips：容器找到对应的servlet处理请求？ 通过Mapper映射
4.  tomcat的结构？
5.  tomcat一键启动
6.  tomcat启动速度优化
7.  jetty结构？
8.  为什么要面向接口编程
9.  计算机IO
    