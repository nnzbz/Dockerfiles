# 选择一个已有的os镜像作为基础
FROM centos

# 镜像的作者和邮箱
MAINTAINER zbz "nnzbz@163.com"

# 时区修改为上海
ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# 设置utf-8，统一编码格式
ENV LC_ALL en_US.UTF-8

# 加入jre
ADD server-jre-8u172-linux-x64.tar.gz /usr/local/jvm
# 加入JCE
ADD UnlimitedJCEPolicyJDK8/*.jar /usr/local/jvm/jdk1.8.0_172/lib/security/

# 设置环境变量
ENV JAVA_HOME /usr/local/jvm/jdk1.8.0_172
ENV PATH $JAVA_HOME/bin:$PATH