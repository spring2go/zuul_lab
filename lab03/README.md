实验三、后置过滤器实验
======

### 实验步骤

#### 1. 在Eclipse中启动lab05的Student服务

[Student Service](https://github.com/spring2go/zuul_lab/tree/master/lab05/student-service)


#### 2. 启用配置项

配置文件:
[mobile_zuul.properties](https://github.com/spring2go/s2g-zuul/blob/master/s2g-zuul-mobile/src/main/resources/mobile_zuul.properties)

配置项:
```
zuul.include.debug.header=true
```

#### 3. 在Eclipse中启动Zuul+Tomcat服务器

通过Postman校验
```
http://localhost:8080/s2g-zuul-mobile/healthcheck
```
#### 4. 通过过滤器管理工具加载并激活后置过滤器

过滤器管理工具：
```
http://localhost:8080/s2g-zuul-mobile/admin/filterLoader.jsp
```

加载并激活：

* 后置过滤器[DebugHeader.groovy](https://github.com/spring2go/s2g-zuul/blob/master/s2g-zuul-mobile/src/scripts/post/DebugHeader.groovy)

通过Postman校验
```
http://localhost:8080/s2g-zuul-mobile/api/student/echoStudentName/bobo
```

通过Eclipse控制台输出查看过滤器调试日志

