实验一、前置过滤器实验
======


### 实验步骤

#### 1. 在Eclipse中启动Zuul+Tomcat服务器

通过Postman校验
```
http://localhost:8080/s2g-zuul-mobile/
```
#### 2. 通过过滤器管理工具加载并激活过滤器

过滤器管理工具：
```
http://localhost:8080/s2g-zuul-mobile/admin/filterLoader.jsp
```

加载并激活：

* 前置过滤器
* 后置过滤器
* 错误过滤器

通过Postman校验
```
http://localhost:8080/s2g-zuul-mobile/healthcheck
```

通过Eclipse控制台输出查看过滤器调试日志

### 实验代码

#### 前置过滤器

1. 调试模式设置过滤器[DebugModeSetter.groovy](https://github.com/spring2go/s2g-zuul/blob/master/s2g-zuul-mobile/src/scripts/pre/DebugModeSetter.groovy)
2. 调试请求过滤器[DebugRequest.groovy](https://github.com/spring2go/s2g-zuul/blob/master/s2g-zuul-mobile/src/scripts/pre/DebugRequest.groovy)
3. 健康检查过滤器[HealthCheck](https://github.com/spring2go/s2g-zuul/blob/master/s2g-zuul-mobile/src/scripts/pre/HealthCheck.groovy)
4. 选路由过滤器[TestRoute.groovy](https://github.com/spring2go/s2g-zuul/blob/master/s2g-zuul-mobile/src/scripts/pre/TestRoute.groovy)

#### 后置过滤器

1. 发送响应过滤器[SendResponse.groovy](https://github.com/spring2go/s2g-zuul/blob/master/s2g-zuul-mobile/src/scripts/post/SendResponse.groovy)
2. 调试HTTP头过滤器[DebugHeader.groovy](https://github.com/spring2go/s2g-zuul/blob/master/s2g-zuul-mobile/src/scripts/post/DebugHeader.groovy)
3. 调试响应过滤器[DebugResponse.groovy](https://github.com/spring2go/s2g-zuul/blob/master/s2g-zuul-mobile/src/scripts/post/DebugResponse.groovy) 

#### 错误过滤器

1. 错误响应过滤器[ErrorResponse.groovy](https://github.com/spring2go/s2g-zuul/blob/master/s2g-zuul-mobile/src/scripts/error/ErrorResponse.groovy)