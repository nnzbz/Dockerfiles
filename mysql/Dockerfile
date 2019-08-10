# 选择一个已有的os镜像作为基础
FROM mysql:5
# 镜像的作者和邮箱
MAINTAINER zbz "nnzbz@163.com"

# 时区修改为上海
ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# 让系统支持统一的编码格式
RUN apt-get update && \
    apt-get install -y locales && \
    locale-gen C.UTF-8 && \
    /usr/sbin/update-locale LANG=C.UTF-8 && \
    apt-get remove -y locales
# 设置utf-8，统一编码格式
ENV LANG C.UTF-8

# 修改权限
RUN chmod 1777 -R /tmp

# 创建安全文件夹并设置权限
#RUN mkdir -p /var/lib/mysql-files
#RUN chmod 1777 -R /var/lib/mysql-files


# 修改my.cnf文件支持utf-8
RUN mv /etc/mysql/my.cnf /etc/mysql/my.cnf.bak
RUN echo "[client]" >>/etc/mysql/my.cnf
RUN echo "default-character-set=utf8mb4" >>/etc/mysql/my.cnf

RUN echo "[mysql]" >>/etc/mysql/my.cnf
RUN echo "default-character-set=utf8mb4" >>/etc/mysql/my.cnf

RUN echo "[mysqld]" >>/etc/mysql/my.cnf
RUN echo "character-set-client-handshake=FALSE" >>/etc/mysql/my.cnf
RUN echo "character-set-server=utf8mb4" >>/etc/mysql/my.cnf
RUN echo "collation-server=utf8mb4_general_ci" >>/etc/mysql/my.cnf
