实验五、Spring Cloud Zuul实验
======

### 实验步骤

#### 1. 在Eclipse中启动lab05的Student服务

[Student Service](https://github.com/spring2go/zuul_lab/tree/master/lab05/student-service)


#### 2. 在Eclipse中启动Lab05的Spring Cloud Zuul网关服务

[Spring Cloud Zuul Service](https://github.com/spring2go/zuul_lab/tree/master/lab05/zuul_gateway)

#### 3. 校验

* 通过Postman校验
```
http://localhost:8080/student/echoStudentName/bobo
http://localhost:8080/student/getStudentDetails/bobo
```

* 通过Eclipse控制台校验

