实验二、路由过滤器实验
======

### 实验步骤

#### 1. 在Eclipse中启动lab05的Student服务

[Student Service](https://github.com/spring2go/zuul_lab/tree/master/lab05/student-service)

#### 2. 添加路由配置项

配置文件:
[mobile_zuul.properties](https://github.com/spring2go/s2g-zuul/blob/master/s2g-zuul-mobile/src/main/resources/mobile_zuul.properties)

配置项:
```
zuul.routing_table_string=student@http://localhost:9700&hello@http://localhost:9700
```


#### 3. 在Eclipse中启动Zuul+Tomcat服务器

通过Postman校验
```
http://localhost:8080/s2g-zuul-mobile/healthcheck
```
#### 4. 通过过滤器管理工具加载并激活路由过滤器

过滤器管理工具：
```
http://localhost:8080/s2g-zuul-mobile/admin/filterLoader.jsp
```

加载并激活：

* 测试用选路过滤器[TestRoute.groovy](https://github.com/spring2go/s2g-zuul/blob/master/s2g-zuul-mobile/src/scripts/pre/TestRoute.groovy)
* 路由执行过滤器[ExecuteRoute.groovy](https://github.com/spring2go/s2g-zuul/blob/master/s2g-zuul-mobile/src/scripts/route/ExecuteRoute.groovy)

#### 5.校验

通过Postman校验
```
http://localhost:8080/s2g-zuul-mobile/api/student/echoStudentName/bobo
http://localhost:8080/s2g-zuul-mobile/api/student/getStudentDetails/bobo
```

通过Eclipse控制台输出查看过滤器调试日志

