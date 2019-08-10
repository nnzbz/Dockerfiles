# 选择一个已有的os镜像作为基础
FROM centos:7

# 镜像的作者和邮箱
LABEL maintainer="nnzbz@163.com"
# 镜像的版本
LABEL version="1.0.0"
# 镜像的描述
LABEL description="base CentOS7 and integrate JDK8 \
基于CentOS7系统，集成了JDK8的环境"

# 时区修改为上海
ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# 设置utf-8，统一编码格式
ENV LC_ALL en_US.UTF-8

# 加入jre（docker好像并不支持解压此版本的压缩文件）
# ADD jdk-8u202-linux-x64.tar.gz /usr/local/jvm
COPY jdk1.8.0_202/ /usr/local/jvm/jdk1.8.0_202
# 加入JCE
COPY UnlimitedJCEPolicyJDK8/*.jar /usr/local/jvm/jdk1.8.0_202/lib/security/
# 加入供jstatd监控使用的安全策略文件
COPY jstatd.all.policy /usr/local/jvm/

# 设置环境变量
ENV JAVA_HOME /usr/local/jvm/jdk1.8.0_202
ENV PATH $JAVA_HOME/bin:$PATH