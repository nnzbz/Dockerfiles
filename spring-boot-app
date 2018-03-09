# 基础镜像
FROM nnzbz/centos-jre
# 作者及邮箱
MAINTAINER zbz <nnzbz@163.com>

# 设置工作目录
WORKDIR /usr/local/myservice

# 运行服务
ENTRYPOINT ["/bin/bash", "-c", "java -Djava.security.egd=file:/dev/./urandom -server -jar myservice.jar"]
