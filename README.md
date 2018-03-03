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
### 改
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

## 子句

### EHERE 条件
```
WHERE name='test'
WHERE age>18
WHERE age>18 AND score<60
WHERE age>18 OR score<60
```
### ORDER 排序
```
ORDER BY age ASE 
ORDER BY age DESC
ORDER BY age DESC,sales DESC
```
## 集群
```
SELECT * FROM user_table GROUP BY calss
SELECT calss,COUNT(class) FROM user_table GROUP BY calss
COUNT(字段) // 计数
MAX(字段)   // 最大值
MIN(字段)   // 最小值
AVG(字段)   // 平均数
SUM(字段)   // 求和
```
### LIMIT 
```
LIMIT 5
// 限制输出前五条
LIMIT 5，8
// 从第五条开始要8条
```

## 顺序
```
WHERE GROUP ORDER LIMIT
```
