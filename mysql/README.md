# nnzbz/mysql

## 1. 特性

1. mysql
2. TZ=Asia/Shanghai
3. C.UTF-8
4. my.cnf -> utf8mb4

## 2. 拉取与制作标签

1. pull

在自动编译后，拉取下来

```sh
docker pull nnzbz/mysql
```

2. tag

```sh
docker tag nnzbz/mysql:latest nnzbz/mysql:1.0.0
```

3. push

```sh
docker push nnzbz/mysql:1.0.0
```

## 3. 创建并运行容器

```sh
# 创建MySQL的数据卷
docker run --name mysql-data nnzbz/mysql echo "data-only container for MySQL"
# 创建并运行MySQL的容器
docker run -dp3306:3306 --restart=always --name mysql -e MYSQL_ROOT_PASSWORD=root --volumes-from mysql-data nnzbz/mysql
```

## 4. 其它容器连接MySQL容器

```sh
docker run --name some-app --link some-mysql:mysql -d application-that-uses-mysql
```