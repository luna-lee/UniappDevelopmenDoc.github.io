# 数据库操作 封装方法
## openDB  
- 打开数据库
- 参数：name  数据库名
- 参数：path  数据库存放地址文件
- 返回一个prmoise， 成功后 返回数据，失败返回false 

参数|说明|类型|默认值
 ---|---|---|---
 name|数据库名|String|local
 path|数据库存放地址文件|String|_doc/local-database.db

``` javascript
await this.$utils.db.openDB()    
await this.$utils.db.openDB({name:"xxx",path:"_doc/xxx.db"})     
```

## isOpenDatabase  
- 判断数据库是否打开
- 参数：name  数据库名
- 参数：path  数据库存放地址文件

参数|说明|类型|默认值
 ---|---|---|---
 name|数据库名|String|local
 path|数据库存放地址文件|String|_doc/local-database.db

``` javascript
  this.$utils.db.isOpenDatabase()      
  this.$utils.db.isOpenDatabase({name:"xxx",path:"_doc/xxx.db"})     
```

## closeDB  
- 关闭数据库
- 参数：name  数据库名
- 参数：path  数据库存放地址文件
- 返回一个prmoise， 成功后 返回数据，失败返回false 

参数|说明|类型|默认值
 ---|---|---|---
 name|数据库名|String|local
 path|数据库存放地址文件|String|_doc/local-database.db

``` javascript
await this.$utils.db.closeDB()    
await this.$utils.db.closeDB({name:"xxx",path:"_doc/xxx.db"})     
```

## executeSql  
- 数据库打开后执行增删改等操作的SQL语句
- 参数：name  数据库名
- 参数：sql  sql语句
- 返回一个prmoise， 成功后 返回数据，失败返回false 

参数|说明|类型|默认值
 ---|---|---|---
 name|数据库名|String|local
 sql|sql语句|String|''

``` javascript
await this.$utils.db.executeSql({sql:"create table if not exists called("phone" CHAR(110),"callTime" CHAR(100),"callDuration" CHAR(100),"callTypeCode" CHAR(100),"callStatus" INT(11),"connectedStatus" INT(11))"})    
await this.$utils.db.executeSql({sql:"insert into called values('xx','xx','xx','xx','xx','xx')",name:"xxx"})     
```

## selectSQL  
- 查询SQL语句
- 参数：name  数据库名
- 参数：path  数据库存放地址文件
- 返回一个prmoise， 成功后 返回数据，失败返回false 

参数|说明|类型|默认值
 ---|---|---|---
 name|数据库名|String|local
 sql|sql语句|String|''
 
``` javascript
const res=await this.$utils.db.selectSQL({sql:"select * from called"})    
const res=await this.$utils.db.selectSQL({sql:"select * from called",name:"xxx"})      
```

## 表模块 
- fileDB 将服务端文件下载到本地，并将本地的文件名与服务端名关联。 非app端则直接返回Url