# 选择一个已有的os镜像作为基础
FROM centos

# 镜像的作者和邮箱
MAINTAINER zbz "nnzbz@163.com"

# 时区修改为上海
ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# 设置utf-8，统一编码格式
ENV LC_ALL en_US.UTF-8

# 复制jre
ADD http://download.oracle.com/otn-pub/java/jdk/8u162-b12/0da788060d494f5095bf8624735fa2f1/server-jre-8u162-linux-x64.tar.gz /usr/local/jvm

# 设置环境变量
ENV JAVA_HOME /usr/local/jvm/jdk1.8.0_162
ENV PATH $JAVA_HOME/bin:$PATH
