1.  什么是HTTP？
    http协议的本质是一种浏览器与服务器之间约定好的通讯格式
2.  什么是servlet接口？
    servlet接口其实是servlet容器跟具体业务之间的接口。servlet接口定义了5个方法分别是：init、getServletConfig、service、getServletInfo和destroy。其中最终要的是service，具体业务类在这个方法里实现处理逻辑。
3.  servlet的容器主要作用是什么？
    servlet容器主要作用是IO流转换处理（客户端请求解析将HttpRequest转换成servletRequest，然后交给servlet处理，servlet处理完的结果servletResponse转换成httpResponse），和servlet的管理。tips：容器找到对应的servlet处理请求？ 通过Mapper映射
4.  tomcat的结构？
    tomcat主要分成两部分 连接器Connector和容器Container。 Container是一个分层组件架构，包含4个子容器 Engine、host、context、wrapper。
    Engine：引擎，用来管理多个站点，一个service最多只能有一个Engine。
    host：代表一个站点，也可以叫虚拟主机，通过配置host就可以添加站点。 一个engine下可以由多个host
    context：代表着一个应用程序，对应平时开发的一套应用程序。或者一个WEN-INF目录及下面的web.xml文件。 一个host下可以对应多个context
    wrapper：每一个wrapper封装着一个servlet。 一个context下可以有多个wrapper
5.  tomcat一键启动
    使用责任链的设计模式，调用父容器的start时，父容器调用子容器的start方法。
6.  tomcat启动速度优化
    1） 清除不必要的web应用，首先我们需要删除webapps文件夹下不需要的工程，一般是example、doc等默认工程、还有以前添加的但现在用不着的工程，最好把这些全部删掉，应为tomcat每次启动时都会重新不是webapps下面的工程。
    2） 清除xml配置文件 tomcat启动时会解析所有的xml配置文件，但xml解析的代价可不小，因此我们要尽量保持配置文件简洁，需要解析的数据越少，自然就越快。
    3） 清除jar文件 我们还可已删除不需要的jar文件，jvm的类加载器在加载类时，需要查找每一个jar文件，去找到所需的类，如果删除了不需要的jar文件，查找速度就会快一些
    4） 清理其他文件 及时清理日志，删除 logs 文件夹下不需要的日志文件
    5） 禁止tomcatTLD扫描 Tomcat 为了支持 JSP，在应用启动的时候会扫描 JAR 包里面的 TLD 文件，加载里面定义的标签库。禁止方法找到 Tomcat 的conf/目录下的context.xml文件，在这个文件里 Context 标签下，加上JarScanner和JarScanFilter子标签
7.  jetty结构？
    由一系列Connector和一系类handler和一个线程池组成。
8.  为什么要面向接口编程
    接口就相当于一套规范，实现同一个接口就相当于实现了同一个规范，然后不同的厂商只需实现这个规范就行，如JDBC实现。
9.  计算机IO
    