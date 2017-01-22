一.SpringMVC 所需的jar包

spring-aop-4.00.RELEASE.jar
spring-beans-4.00.RELEASE.jar
spring-context-4.00.RELEASE.jar
spring-core-4.00.RELEASE.jar
spring-expression-4.00.RELEASE.jar
spring-web-4.00.RELEASE.jar
spring-webMvc-4.00.RELEASE.jar 
commons-logging-1.1.1.jar  日志


####springmvc    
1.web.xml配置dispatcherServlet. 处理所有的请求。

2.spring的主配置文件可以通过
1).
<init-param>
  <param-name>contextConfigLocation</param-name>
  <param-value>spring.xml</param-value>
</init-param>配置
2).
也可以通过默认的配置地址 /WEB-INF/<servlet-name>-servlet.xml 的方式进行配置。

3.注解.
1).@controller 告诉spring这是个控制器。
   @requestMapping("/request1")在类前添加时 告诉控制器这个请求所映射的类。
   @requestMapping("/request2")在方法前添加时 告诉控制器这个请求对应的方法。若该方法的类也有@requestMapping();时，那请求路径就要将类前的加上。
   @requestMapping(value="/request3",method=requestMethod.POST);//指定请求方式，若此时请求路径正确，请求方式错误，则抛出405异常。
   @requestMapping();中可以放入参数 params 和hearders 来进行过滤。
4.pojo.通过在表单中设置标签的name属性进行相应的参数值传递到相应的对象，并根据参数值，对对象赋值。也可以通过级联属性进行赋值。
