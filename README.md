# mysql

操作数据库需要安装客户端和服务端，Navicat是服务端，客户端要安装`mysql`
安装完成需要配置
```js
const mysql = require('mysql')
const db = mysql.createPool(
  {
    host: 'localhost',
    user: 'root',
    password: '123456',
    database: 'learn'
  }
)
```

然后通过`db.query(数据库查询语句，回调函数)`形式与数据库交互

## 数据库查询语句

### 增
```
INSERT INTO 表 （字段列表） VALUES （值列表）
INSERT INTO user_table (username,password) VALUES ('my','123')
```
### 删
删除`user_table`数据库中`ID=1`的数据
```
DELETE FROM 表 EHERE 条件
DELETE FROM user_table WHERE ID=1
```
### 该
```
UPDATE 表 SET 字段=值，字段=值 WHERE 条件
UPDATE admin_table SET username='min',password='456' WHERE ID=2
```
### 查
选取`user_table`数据库中`ID=1`的数据，注意数据库里面的数据类型，如果ID是字符串，那么就要写成`ID='1'`
```
SELECT * FROM 表
SELECT * FROM user_table WHERE ID=1
```
