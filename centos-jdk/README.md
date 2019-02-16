# CentOS-JDK

## 1. 简要说明

基于CentOS系统，集成了JDK8的环境

## 2. 特性

1. centos 7.4.1708
2. server jdk 1.8.0_202
3. JCE
4. TZ=Asia/Shanghai
5. en_US.UTF-8
6. JAVA_HOME=/usr/local/jvm/jdk1.8.0_202/

## 3. 创建并运行容器

```sh
docker run -d --name centos-jdk -it nnzbz/centos-jdk /bin/sh
```

## 4. 进入容器

```sh
docker exec -it centos-jdk /bin/bash
```

## 5. 如果要运行jstatd监控

进入容器中，执行如下命令（注意不能退出）

```sh
jstatd -J-Djava.security.policy=/usr/local/jvm/jstatd.all.policy
```