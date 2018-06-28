实验四、Zuul网关对接Apollo
======

### 实验步骤

#### 1. 在Eclipse中启动lab05的Student服务

[Student Service](https://github.com/spring2go/zuul_lab/tree/master/lab05/student-service)


#### 2. 启用Apollo配置中心本地版

```
./demo.sh start
```

[参考Apollo Quick Start](https://github.com/ctripcorp/apollo/wiki/Quick-Start)


#### 3. 在Eclipse中启动Zuul+Tomcat服务器

修改服务器端口为`9000`，避免和Apollo的Config Service端口(8080)冲突

通过Postman校验
```
http://localhost:9000/s2g-zuul-mobile/healthcheck
```
#### 4. 通过Apollo调整配置项

Apollo管理界面
```
http://localhost:8070
```

动态配置项
```
zuul.could.set.debug=false
zuul.routing_table_string=student@http://localhost:9700&testapi@http://localhost:9700
```

#### 5. 校验

1. 通过Postman校验
```
http://localhost:9000/s2g-zuul-mobile/api/testapi/echoStudentName/bobo
```

2. 通过Eclipse控制台输出查看过滤器调试日志

3. 通过InfoBoard工具校验
```
http://localhost:8077
```
