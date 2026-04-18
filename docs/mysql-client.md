# mysql指南

## 安装

```bash
brew install mysql-client
echo 'export PATH="/opt/homebrew/opt/mysql-client/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc

mysql --version
```

## 连接

### 客户端连接服务

```bash
mysql -h 主机名 -P 端口 -u 用户名 -p --default-character-set=utf8mb4
```

### 客户端中文改编码

```mysql
SET NAMES utf8mb4;
```

## 导出整个库/表

```bash
mysqldump -h 主机 -u 用户 -p --default-character-set=utf8mb4 mydb [mytable] > ~/Desktop/mydb_backup.sql
```

其它参数

![](https://s2.loli.net/2025/08/17/nqUbuoGyYxt7OvE.png)