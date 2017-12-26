<h1 align="center">mongodb的使用</h1>


## 1、 mongodb需要了解的一些概念
* database 数据库 <br>

  mongodb数据库存储在data目录中 <br>
  show dbs 显示所有的数据库 <br>
  use mydb 创建和切换数据库 <br>
  
* collection 集合，数据库表，table  <br>
 
  集合是mongodb文档组，存储在数据库中，没有固定的结构，可以插入不同格式和类型的数据。<br>
  capped collections 固定大小的集合，有很高的性能以及队列过期的特性，需要显式创建，指定集合的大小，提前分配存储空间。<br>
  向集合插入数据，如果集合不存在则会创建集合。<br>
    
* document 数据记录行/文档，row <br>

  文档是一组键/值对（BSON）,mongodb的文档不需要设置相同的字段，并且相同的字段不需要相同的数据类型。文档的键值对是有序的。mongodb区分类型和大小写。不能有重复的键。键是字符串，特殊情况可以使utf-8字符。<br>
  BSON is a binary serialization format used to store documents and make remote procedure calls in MongoDB. 
  
* field 字段/域、column <br>
  mongodb支持的常用数据类型：
  
  <table>
  <tr>
    <td>数据类型</td><td>描述</td>
  </tr>
    <tr>
    <td>String</td><td>字符串，mongodb中utf-8编码的字符串才是合法的</td>
  </tr>
    <tr>
    <td>Integer</td><td>整型数值</td>
  </tr>
    <tr>
    <td>Boolean</td><td>布尔值</td>
  </tr>
    <tr>
    <td>Double</td><td>双精度浮点数</td>
  </tr>
    <tr>
    <td>Array</td><td>数组</td>
  </tr>
    <tr>
    <td>Timestamp</td><td>时间戳</td>
  </tr>
    <tr>
    <td>Object</td><td>内嵌文档</td>
  </tr>
    <tr>
    <td>Null</td><td>用于创建空值</td>
  </tr>
    <tr>
    <td>Date</td><td>日期时间</td>
  </tr>
    <tr>
    <td>Object ID</td><td>对象ID，用于创建文档ID</td>
  </tr>
    <tr>
    <td>Binary Data</td><td>二进制数据</td>
  </tr>
  <tr>
    <td>Code</td><td>代码类型。用于在文档中存储 JavaScript 代码。</td>
  </tr>
  </tr>
    <tr>
    <td>Min/Max keys</td><td>将一个值与 BSON（二进制的 JSON）元素的最低值和最高值相对比</td>
  </tr>
   <tr>
    <td>Symbol</td><td>符号。该数据类型基本上等同于字符串类型，但不同的是，它一般用于采用特殊符号类型的语言。</td>
  </tr>
  <tr>
    <td>Regular expression</td><td>正则表达式类型。用于存储正则表达式。</td>
  </tr>
  </table>

  
* index 索引 <br>
   
* primary key  主键，mongodb自动将_id字段设置为主键 <br>

## 2、 mongodb的连接

标准 URI 连接语法：
	<pre><code>
	mongodb://[username:password@]host1[:port1][,host2[:port2],...[,hostN[:portN]]][/[database][?	options]]
	</code></pre>
 mongodb:// 这是固定的格式，必须要指定。<br>
 username:password@ 可选项，如果设置，在连接数据库服务器之后， 驱动都会尝试登陆这个数据库.<br>
 host1:连接服务器 <br>
 portN:连接端口，默认27017 <br>
 database:默认数据库，不指定是test <br>
 option:连接选项 <br>
  
## 3、mongodb CRUD 操作

### 3.1 create database

<pre><code>
rs0: PRIMARY> use mydb
switched to db mydb
rs0: PRIMARY> db
mydb
</code></pre>

如果数据库存在则切换到数据库，如果不存在则创建。使用'show dbs'查看所有数据库，自己创建的数据库中必须存在document，才能显示。'db'，查看当前数据库。

### 3.2 drop database

<pre><code>
rs0: PRIMARY> use mydb
switched to db mydb
rs0: PRIMARY> db
mydb
rs0: PRIMARY> db.dropDatabase()
{ "dropped" : "mydb", "ok" : 1 }
</code></pre>

### 3.3 create collection

<pre><code>
rs0: PRIMARY> use mydb
switched to db mydb
rs0: PRIMARY> db
mydb
rs0: PRIMARY> db.mycollection.insert({'name':'insert test','note':'insert learn'})
WriteResult({ "nInserted" : 1 })
rs0: PRIMARY> db.mycollection.find()
{ "_id" : ObjectId("5a4056a146245769d3e9e032"), "name" : "insert test", "note" : "insert learn" }
</code></pre>

以上，'_id'没有指定，自动增加了，使用find()查询插入结果。
插入数据，如果集合不存在则会创建集合。


### 3.4 drop collection

<pre><code>
rs0: PRIMARY> db
mydb
rs0: PRIMARY> show tables;
mycollection
rs0: PRIMARY> db.mycollection.drop()
true
rs0: PRIMARY> show tables;
rs0: PRIMARY> 
rs0: PRIMARY> 
</code></pre>

'show tables'查看集合集。

### 3.5 insert

插入一条document到collection中，如果collection不存在，则创建collection。

* insert()插入单条记录

<pre><code>
rs0: PRIMARY> db.mycollection.insert({'name':'insert one','note':'insert learn'})
WriteResult({ "nInserted" : 1 })
</code></pre>

* insert()插入多条记录

<pre><code>
rs0: PRIMARY> db.mycollection.insert([{'name':'delete one','note':'delete learn'},{'name':'delete two','note':'delete learn'},{'name':'delete three','note':'delete learn'}])
BulkWriteResult({
	"writeErrors" : [ ],
	"writeConcernErrors" : [ ],
	"nInserted" : 3,
	"nUpserted" : 0,
	"nMatched" : 0,
	"nModified" : 0,
	"nRemoved" : 0,
	"upserted" : [ ]
})
) 
</code></pre>

* insertOne()插入单条记录

<pre><code>
rs0: PRIMARY> db.mycollection.insertOne({'name':'delete one','note':'delete learn'})
{
	"acknowledged" : true,
	"insertedId" : ObjectId("5a406da246245769d3e9e048")
}
</code></pre>

* insertMany()插入多条记录

<pre><code>
rs0: PRIMARY> db.mycollection.insertMany([{'name':'delete one','note':'delete learn'},{'name':'delete two','note':'delete learn'},{'name':'delete three','note':'delete learn'}])
{
	"acknowledged" : true,
	"insertedIds" : [
		ObjectId("5a406d6f46245769d3e9e045"),
		ObjectId("5a406d6f46245769d3e9e046"),
		ObjectId("5a406d6f46245769d3e9e047")
	]
}
</code></pre>

### 3.6 update

* update更新一条记录

<pre><code>
rs0: PRIMARY> db.mycollection.insert({'name':'insert only one','note':'insert learn'})
WriteResult({ "nInserted" : 1 })
rs0: PRIMARY> db.mycollection.insert({'name':'insert only one','note':'insert learn'})
{
	"acknowledged" : true,
	"insertedId" : ObjectId("5a4058de46245769d3e9e034")
}
rs0: PRIMARY> db.mycollection.find()
{ "_id" : ObjectId("5a4058bf46245769d3e9e033"), "name" : "insert only one", "note" : "insert learn" }
{ "_id" : ObjectId("5a4058de46245769d3e9e034"), "name" : "insert only one", "note" : "insert learn" }
rs0: PRIMARY> db.mycollection.update({'name':'insert only one'},{$set:{'name':'update test'}})
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
rs0: PRIMARY> db.mycollection.find()
{ "_id" : ObjectId("5a4058bf46245769d3e9e033"), "name" : "update test", "note" : "insert learn" }
{ "_id" : ObjectId("5a4058de46245769d3e9e034"), "name" : "insert only one", "note" : "insert learn" }
</code></pre>

* 如果要修改多条相同的document，需要增加multi参数为true。

<pre><code>
 rs0: PRIMARY> db.mycollection.update({'note':'insert learn'},{$set:{'note':'update learn'}},{multi:true})
WriteResult({ "nMatched" : 2, "nUpserted" : 0, "nModified" : 2 })
 rs0: PRIMARY> db.mycollection.find()
{ "_id" : ObjectId("5a4058bf46245769d3e9e033"), "name" : "update test", "note" : "update learn" }
{ "_id" : ObjectId("5a4058de46245769d3e9e034"), "name" : "insert only one", "note" : "update learn" }
</code></pre>

* 其他更新语句

<pre><code>
db.mycollection.updateOne()
db.mycollection.updateMany()
db.mycollection.replaceOne()
</code></pre>

### 3.7 delete
插入多条记录
<pre><code>
rs0: PRIMARY> db.mycollection.insert([{'name':'delete one','note':'delete learn'},{'name':'delete two','note':'delete learn'},{'name':'delete three','note':'delete learn'}])
BulkWriteResult({
	"writeErrors" : [ ],
	"writeConcernErrors" : [ ],
	"nInserted" : 3,
	"nUpserted" : 0,
	"nMatched" : 0,
	"nModified" : 0,
	"nRemoved" : 0,
	"upserted" : [ ]
})
</code></pre>

* 删除一条记录

<pre><code>
rs0: PRIMARY> db.mycollection.deleteOne({'name':'delete one'})
{ "acknowledged" : true, "deletedCount" : 1 }
</code></pre>

* 删除多条记录

<pre><code>
rs0: PRIMARY> db.mycollection.deleteMany({'note':'delete learn'})
{ "acknowledged" : true, "deletedCount" : 2 }
</code></pre>

* 删除所有记录

<pre><code>
rs0: PRIMARY> db.mycollection.remove({})
</code></pre>

### 3.8 bulkWrite

<pre><code>
db.collection.bulkWrite(
   [
      { insertOne : <document> },
      { updateOne : <document> },
      { updateMany : <document> },
      { replaceOne : <document> },
      { deleteOne : <document> },
      { deleteMany : <document> }
   ],
   { ordered : false }
)
</code></pre>

### 3.9 query

####（1）查询所有记录
 
 <pre><code>
rs0: PRIMARY> db.mycollection.find()
SQL : select * from mycollection;
</code></pre>

####（2）条件查询

<pre><code>
rs0: PRIMARY> db.mycollection.find({'status':1})
SQL : select * from mycollection where status = 1
</code></pre>

####（3）in查询

<pre><code>
rs0: PRIMARY> db.mycollection.find({'status':{$in[1,2]}})
SQL : select * from mycollection where status in (1, 2)
</code></pre>

####（4）and查询

<pre><code>
rs0: PRIMARY> db.mycollection.find({'status':1,level:{$lt:3}})
SQL : select * from mycollection where status = 1 and level < 3
</code></pre>

####（5）or查询

<pre><code>
rs0: PRIMARY> db.mycollection.find({$or:[{'status':1},{'level':{$lt:3}}]})
SQL : select * from mycollection where status = 1 or level < 3
</code></pre>

####（6）and or 查询

<pre><code>
rs0: PRIMARY> db.mycollection.find({'status':1, $or:[{'level':{$lt:3}},{'time':{$gt:3}}]})
SQL : select * from mycollection where status = 1 or (level < 3 and time > 3)
</code></pre>

####（7）嵌入式Embedded/Nested查询

<pre><code>
rs0:PRIMARY> db.mytest.insert( [
...    { item: "journal", qty: 25, size: { h: 14, w: 21, uom: "cm" }, status: "A" },
...    { item: "notebook", qty: 50, size: { h: 8.5, w: 11, uom: "in" }, status: "A" },
...    { item: "paper", qty: 100, size: { h: 8.5, w: 11, uom: "in" }, status: "D" },
...    { item: "planner", qty: 75, size: { h: 22.85, w: 30, uom: "cm" }, status: "D" },
...    { item: "postcard", qty: 45, size: { h: 10, w: 15.25, uom: "cm" }, status: "A" }
... ]);
BulkWriteResult({
	"writeErrors" : [ ],
	"writeConcernErrors" : [ ],
	"nInserted" : 5,
	"nUpserted" : 0,
	"nMatched" : 0,
	"nModified" : 0,
	"nRemoved" : 0,
	"upserted" : [ ]
})

rs0:PRIMARY> db.mytest.find({'size':{h:14,w:21,uom:'cm'}})
{ "_id" : ObjectId("5a40974246245769d3e9e049"), "item" : "journal", "qty" : 25, "size" : { "h" : 14, "w" : 21, "uom" : "cm" }, "status" : "A" }

rs0:PRIMARY> db.mytest.find({'size.h':{$gt:14}})
{ "_id" : ObjectId("5a40974246245769d3e9e04c"), "item" : "planner", "qty" : 75, "size" : { "h" : 22.85, "w" : 30, "uom" : "cm" }, "status" : "D" }

rs0:PRIMARY> db.mytest.find( { "size.h": { $lt: 15 }, "size.uom": "in", status: "D" } )
{ "_id" : ObjectId("5a40974246245769d3e9e04b"), "item" : "paper", "qty" : 100, "size" : { "h" : 8.5, "w" : 11, "uom" : "in" }, "status" : "D" }
</code></pre>

####（8）array查询

插入测试数据
<pre><code>
rs0:PRIMARY> db.mytest.insertMany([
...    { item: "journal", qty: 25, tags: ["blank", "red"], dim_cm: [ 14, 21 ] },
...    { item: "notebook", qty: 50, tags: ["red", "blank"], dim_cm: [ 14, 21 ] },
...    { item: "paper", qty: 100, tags: ["red", "blank", "plain"], dim_cm: [ 14, 21 ] },
...    { item: "planner", qty: 75, tags: ["blank", "red"], dim_cm: [ 22.85, 30 ] },
...    { item: "postcard", qty: 45, tags: ["blue"], dim_cm: [ 10, 15.25 ] }
... ]);
{
	"acknowledged" : true,
	"insertedIds" : [
		ObjectId("5a409a4046245769d3e9e04e"),
		ObjectId("5a409a4046245769d3e9e04f"),
		ObjectId("5a409a4046245769d3e9e050"),
		ObjectId("5a409a4046245769d3e9e051"),
		ObjectId("5a409a4046245769d3e9e052")
	]
}
</code></pre>

* 精确查询整个数组

<pre><code>
rs0:PRIMARY> db.mytest.find({'tags':['blank','red']})
{ "_id" : ObjectId("5a409a4046245769d3e9e04e"), "item" : "journal", "qty" : 25, "tags" : [ "blank", "red" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e051"), "item" : "planner", "qty" : 75, "tags" : [ "blank", "red" ], "dim_cm" : [ 22.85, 30 ] }
</code></pre>

* 不按顺序查询数组

<pre><code>
rs0:PRIMARY> db.mytest.find({'tags':{$all:['blank','red']}})
{ "_id" : ObjectId("5a409a4046245769d3e9e04e"), "item" : "journal", "qty" : 25, "tags" : [ "blank", "red" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e04f"), "item" : "notebook", "qty" : 50, "tags" : [ "red", "blank" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e050"), "item" : "paper", "qty" : 100, "tags" : [ "red", "blank", "plain" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e051"), "item" : "planner", "qty" : 75, "tags" : [ "blank", "red" ], "dim_cm" : [ 22.85, 30 ] }
</code></pre>

* 查询数组的一个元素

<pre><code>
rs0:PRIMARY> db.mytest.find({'tags':'red'})
{ "_id" : ObjectId("5a409a4046245769d3e9e04e"), "item" : "journal", "qty" : 25, "tags" : [ "blank", "red" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e04f"), "item" : "notebook", "qty" : 50, "tags" : [ "red", "blank" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e050"), "item" : "paper", "qty" : 100, "tags" : [ "red", "blank", "plain" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e051"), "item" : "planner", "qty" : 75, "tags" : [ "blank", "red" ], "dim_cm" : [ 22.85, 30 ] }
</code></pre>

* 数组的条件查询

<pre><code>
rs0:PRIMARY> db.mytest.find({'dim_cm':{$gt:25}})
{ "_id" : ObjectId("5a409a4046245769d3e9e051"), "item" : "planner", "qty" : 75, "tags" : [ "blank", "red" ], "dim_cm" : [ 22.85, 30 ] }

rs0:PRIMARY> db.mytest.find({'dim_cm':{$gt:22,$lt:25}})
{ "_id" : ObjectId("5a409a4046245769d3e9e051"), "item" : "planner", "qty" : 75, "tags" : [ "blank", "red" ], "dim_cm" : [ 22.85, 30 ] }
</code></pre>

* 指定元素查询

<pre><code>
rs0:PRIMARY> db.mytest.find({'dim_cm.0':{$gt:22}})
{ "_id" : ObjectId("5a409a4046245769d3e9e051"), "item" : "planner", "qty" : 75, "tags" : [ "blank", "red" ], "dim_cm" : [ 22.85, 30 ] }
</code></pre>

* 数组元素个数查询

<pre><code>
rs0:PRIMARY> db.mytest.find({'dim_cm':{$size:2}})
{ "_id" : ObjectId("5a409a4046245769d3e9e04e"), "item" : "journal", "qty" : 25, "tags" : [ "blank", "red" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e04f"), "item" : "notebook", "qty" : 50, "tags" : [ "red", "blank" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e050"), "item" : "paper", "qty" : 100, "tags" : [ "red", "blank", "plain" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e051"), "item" : "planner", "qty" : 75, "tags" : [ "blank", "red" ], "dim_cm" : [ 22.85, 30 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e052"), "item" : "postcard", "qty" : 45, "tags" : [ "blue" ], "dim_cm" : [ 10, 15.25 ] }
rs0:PRIMARY>
rs0:PRIMARY> db.mytest.find({'dim_cm':{$size:3}})
rs0:PRIMARY>
</code></pre>

####（9）数组内嵌

插入测试数据
<pre><code>
rs0:PRIMARY> db.mytest.insertMany( [
...    { item: "journal", instock: [ { warehouse: "A", qty: 5 }, { warehouse: "C", qty: 15 } ] },
...    { item: "notebook", instock: [ { warehouse: "C", qty: 5 } ] },
...    { item: "paper", instock: [ { warehouse: "A", qty: 60 }, { warehouse: "B", qty: 15 } ] },
...    { item: "planner", instock: [ { warehouse: "A", qty: 40 }, { warehouse: "B", qty: 5 } ] },
...    { item: "postcard", instock: [ { warehouse: "B", qty: 15 }, { warehouse: "C", qty: 35 } ] }
... ]);
{
	"acknowledged" : true,
	"insertedIds" : [
		ObjectId("5a409f6446245769d3e9e053"),
		ObjectId("5a409f6446245769d3e9e054"),
		ObjectId("5a409f6446245769d3e9e055"),
		ObjectId("5a409f6446245769d3e9e056"),
		ObjectId("5a409f6446245769d3e9e057")
	]
}
</code></pre>

* 数组内嵌查询，必须按照顺序才能匹配，不按照顺序无法匹配到
 
<pre><code>
rs0:PRIMARY> db.mytest.find( { "instock": { warehouse: "A", qty: 5 } } )
{ "_id" : ObjectId("5a409f6446245769d3e9e053"), "item" : "journal", "instock" : [ { "warehouse" : "A", "qty" : 5 }, { "warehouse" : "C", "qty" : 15 } ] }
rs0:PRIMARY> db.mytest.find( { "instock": { qty: 5,warehouse: "A" } } )
rs0:PRIMARY>
rs0:PRIMARY>
</code></pre>

* 数组字段的条件查询，'.'的使用

<pre><code>
rs0:PRIMARY> db.mytest.find( { "instock.qty": {$gt:40 } } )
{ "_id" : ObjectId("5a409f6446245769d3e9e055"), "item" : "paper", "instock" : [ { "warehouse" : "A", "qty" : 60 }, { "warehouse" : "B", "qty" : 15 } ] }
</code></pre>

* 数组内嵌按元素查询

<pre><code>
rs0:PRIMARY> db.mytest.find( { "instock.0.qty": {$gt:40 } } )
{ "_id" : ObjectId("5a409f6446245769d3e9e055"), "item" : "paper", "instock" : [ { "warehouse" : "A", "qty" : 60 }, { "warehouse" : "B", "qty" : 15 } ] }
rs0:PRIMARY> db.mytest.find( { "instock.1.qty": {$gt:20 } } )
{ "_id" : ObjectId("5a409f6446245769d3e9e057"), "item" : "postcard", "instock" : [ { "warehouse" : "B", "qty" : 15 }, { "warehouse" : "C", "qty" : 35 } ] }
</code></pre>

* 多条件查询

<pre><code>
rs0:PRIMARY> db.mytest.find( { "instock.qty": 5, "instock.warehouse": "A" } )
{ "_id" : ObjectId("5a409f6446245769d3e9e053"), "item" : "journal", "instock" : [ { "warehouse" : "A", "qty" : 5 }, { "warehouse" : "C", "qty" : 15 } ] }
{ "_id" : ObjectId("5a409f6446245769d3e9e056"), "item" : "planner", "instock" : [ { "warehouse" : "A", "qty" : 40 }, { "warehouse" : "B", "qty" : 5 } ] }
</code></pre>

####（10） 返回需要的查询结果

插入测试数据

<pre><code>
db.mytest.insertMany( [
  { item: "journal", status: "A", size: { h: 14, w: 21, uom: "cm" }, instock: [ { warehouse: "A", qty: 5 } ] },
  { item: "notebook", status: "A",  size: { h: 8.5, w: 11, uom: "in" }, instock: [ { warehouse: "C", qty: 5 } ] },
  { item: "paper", status: "D", size: { h: 8.5, w: 11, uom: "in" }, instock: [ { warehouse: "A", qty: 60 } ] },
  { item: "planner", status: "D", size: { h: 22.85, w: 30, uom: "cm" }, instock: [ { warehouse: "A", qty: 40 } ] },
  { item: "postcard", status: "A", size: { h: 10, w: 15.25, uom: "cm" }, instock: [ { warehouse: "B", qty: 15 }, { warehouse: "C", qty: 35 } ] }
]);
</code></pre>

* 返回所有字段

<pre><code>
rs0:PRIMARY> db.mytest.find({'status':'A'})
SQL : select * from mytest where status = 'A'
</code></pre>

* 返回需要的字段

<pre><code>
rs0:PRIMARY> db.mytest.find({'status':'A'},{item:1,status:1})
SQL: select _id,item,status from mytest where status = 'A'
</code></pre>

* 不返回_id

<pre><code>
rs0:PRIMARY> db.mytest.find({'status':'A'},{item:1,status:1,_id:0})
SQL: select item,status from mytest where status = 'A'
</code></pre>

* 返回内嵌文档的某个元素

<pre><code>
rs0:PRIMARY> db.mytest.find({'status':'A'},{item:1,status:1,'size.h':1,_id:0})
{ "item" : "journal", "status" : "A", "size" : { "h" : 14 } }
{ "item" : "notebook", "status" : "A", "size" : { "h" : 8.5 } }
{ "item" : "postcard", "status" : "A", "size" : { "h" : 10 } }
</code></pre>

* 不返回内嵌文档的某个元素，其他的都返回，不能加其他条件了

<pre><code>
rs0:PRIMARY> db.mytest.find({'status':'A'},{'size.h':0})
{ "_id" : ObjectId("5a419b8ecd5b5c783322ef2a"), "item" : "journal", "status" : "A", "size" : { "w" : 21, "uom" : "cm" }, "instock" : [ { "warehouse" : "A", "qty" : 5 } ] }
{ "_id" : ObjectId("5a419b8ecd5b5c783322ef2b"), "item" : "notebook", "status" : "A", "size" : { "w" : 11, "uom" : "in" }, "instock" : [ { "warehouse" : "C", "qty" : 5 } ] }
{ "_id" : ObjectId("5a419b8ecd5b5c783322ef2e"), "item" : "postcard", "status" : "A", "size" : { "w" : 15.25, "uom" : "cm" }, "instock" : [ { "warehouse" : "B", "qty" : 15 }, { "warehouse" : "C", "qty" : 35 } ] }
</code></pre>

* 返回数组元素

<pre><code>
rs0:PRIMARY> db.mytest.find( { status: "A" }, { "instock.qty": 1,_id:0 } )
{ "instock" : [ { "qty" : 5 } ] }
{ "instock" : [ { "qty" : 5 } ] }
{ "instock" : [ { "qty" : 15 }, { "qty" : 35 } ] }
</code></pre>

* 返回数组的最后一个元素

<pre><code>
rs0:PRIMARY> db.mytest.find( { status: "A" }, {instock:{$slice:-1},_id:0,item:1,status:1 } )
{ "item" : "journal", "status" : "A", "instock" : [ { "warehouse" : "A", "qty" : 5 } ] }
{ "item" : "notebook", "status" : "A", "instock" : [ { "warehouse" : "C", "qty" : 5 } ] }
{ "item" : "postcard", "status" : "A", "instock" : [ { "warehouse" : "C", "qty" : 35 } ] }
</code></pre>

#### (11) null值的查询和是否存在某值的查询

插入测试数据
<pre><code>
db.mytest2.insertMany([
   { _id: 1, item: null },
   { _id: 2 }
])
</code></pre>


* null的查询，返回所有null的记录

<pre><code>
rs0:PRIMARY> db.mytest2.find({item:null})
{ "_id" : 1, "item" : null }
{ "_id" : 2 }
</code></pre>

* 返回包含null的记录 <br>
 the value of the item field is of BSON Type Null (type number 10)
 The query returns only the document where the item field has a value of null.
 
<pre><code>
rs0:PRIMARY> db.mytest2.find({item:{$type:10}})
{ "_id" : 1, "item" : null }
</code></pre>

* 查询包含item字段或者不包含item字段的记录，使用$exists

<pre><code>
rs0:PRIMARY> db.mytest2.find({item:{$exists:false}})
{ "_id" : 2 }
rs0:PRIMARY> db.mytest2.find({item:{$exists:true}})
{ "_id" : 1, "item" : null }
</code></pre>

####（12） 创建索引

<pre><code>
db.mytest.createIndex( { user_id: 1,addtime:-1 } )
1 表示正序，-1表示倒序
</code></pre>

