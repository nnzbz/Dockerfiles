# 特性

1. mysql
2. TZ=Asia/Shanghai
3. C.UTF-8
4. my.cnf -> utf8mb4

# 创建并运行容器

```sh
# 创建MySQL的数据卷
docker run --name mysql-data nnzbz/mysql echo "data-only container for MySQL"
# 创建并运行MySQL的容器
docker run -dp3306:3306 --restart=always --name mysql -e MYSQL_ROOT_PASSWORD=root --volumes-from mysql-data nnzbz/mysql
```
