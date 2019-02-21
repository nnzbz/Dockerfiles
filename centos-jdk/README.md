# CentOS-JDK

## 1. 简要说明

基于CentOS系统，集成了JDK8的环境

## 2. 特性

1. CentOS 7.4.1708
2. JDK 1.8.0_202
3. JCE
4. TZ=Asia/Shanghai
5. en_US.UTF-8
6. JAVA_HOME=/usr/local/jvm/jdk1.8.0_202/

## 3. 创建并运行容器

```sh
docker run -d --net=host --name centos-jdk -it nnzbz/centos-jdk /bin/sh
```

## 4. 进入容器

```sh
docker exec -it centos-jdk /bin/bash
```

## 5. 如果要运行jstatd监控

进入容器中，执行如下命令

如果要前台运行（注意Ctrl+C则会关闭程序，直接关闭命令行容器则不会）

```sh
jstatd -J-Djava.rmi.server.hostname=<ip> -J-Dcom.sun.management.jmxremote.authenticate=false -J-Dcom.sun.management.jmxremote.rmi.port=1099 -J-Dcom.sun.management.jmxremote.ssl=false -J-Djava.security.policy=/usr/local/jvm/jstatd.all.policy
```

如果要后台运行

```sh
nohup jstatd -J-Djava.rmi.server.hostname=<ip> -J-Dcom.sun.management.jmxremote.authenticate=false -J-Dcom.sun.management.jmxremote.rmi.port=1099 -J-Dcom.sun.management.jmxremote.ssl=false -J-Djava.security.policy=/usr/local/jvm/jstatd.all.policy >> /usr/local/output.log 2>&1 &
```

- -J-Djava.rmi.server.hostname一定要填写正确的docker容器的宿主IP地址
- jstatd默认端口号是1099，如果要自定义，用 ```-p``` 参数指定端口号
- 运行命令后，可在宿主服务器运行 ```ss -anp | grep 1099``` 查看是否启动成功
