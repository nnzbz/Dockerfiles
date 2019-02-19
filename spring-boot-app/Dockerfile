# 基础镜像
FROM nnzbz/centos-jdk:1.0.0

# 作者及邮箱
# 镜像的作者和邮箱
LABEL maintainer="nnzbz@163.com"
# 镜像的版本
LABEL version="1.0.0"
# 镜像的描述
LABEL description="Environment for Spring Boot Appication\
为运行Spring Boot Application而提供的环境"

# 设置工作目录
WORKDIR /usr/local/myservice

ENV JAVA_OPTS="\ -Xmx800m \ -Xms200m"

# 运行服务
ENTRYPOINT ["/bin/bash", "-c", "java ${JAVA_OPTS} -cp . -Djava.security.egd=file:/dev/./urandom -XX:+UseG1GC -server -jar myservice.jar"]
