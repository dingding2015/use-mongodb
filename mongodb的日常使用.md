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
  mongodb支持的数据类型：
  <pre><code>
  db.collection.insertOne() 
  </code></pre>
  
* index 索引 <br>
   
* primary key  主键，mongodb自动将_id字段设置为主键 <br>

## 2 mongodb的连接

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

* 查询所有记录
 
 <pre><code>
rs0: PRIMARY> db.mycollection.find()
SQL : select * from mytable;
</code></pre>

* 条件查询

<pre><code>
rs0: PRIMARY> db.mycollection.find({'status':1})
SQL : select * from mytable where status = 1
</code></pre>

* in查询

<pre><code>
rs0: PRIMARY> db.mycollection.find({'status':{$in[1,2]}})
SQL : select * from mytable where status in (1, 2)
</code></pre>

* and查询

<pre><code>
rs0: PRIMARY> db.mycollection.find({'status':1,level:{$lt:3}})
SQL : select * from mytable where status = 1 and level < 3
</code></pre>

* or查询

<pre><code>
rs0: PRIMARY> db.mycollection.find({$or:[{'status':1},{'level':{$lt:3}}]})
SQL : select * from mytable where status = 1 or level < 3
</code></pre>

* and or 查询

<pre><code>
rs0: PRIMARY> db.mycollection.find({'status':1, $or:[{'level':{$lt:3}},{'time':{$gt:3}}]})
SQL : select * from mytable where status = 1 or (level < 3 and time > 3)
</code></pre>

* 嵌入式Embedded/Nested查询

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

* array查询

插入test数据
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

精确查询整个数组

<pre><code>
rs0:PRIMARY> db.mytest.find({'tags':['blank','red']})
{ "_id" : ObjectId("5a409a4046245769d3e9e04e"), "item" : "journal", "qty" : 25, "tags" : [ "blank", "red" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e051"), "item" : "planner", "qty" : 75, "tags" : [ "blank", "red" ], "dim_cm" : [ 22.85, 30 ] }
</code></pre>

不按顺序查询数组

<pre><code>
rs0:PRIMARY> db.mytest.find({'tags':{$all:['blank','red']}})
{ "_id" : ObjectId("5a409a4046245769d3e9e04e"), "item" : "journal", "qty" : 25, "tags" : [ "blank", "red" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e04f"), "item" : "notebook", "qty" : 50, "tags" : [ "red", "blank" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e050"), "item" : "paper", "qty" : 100, "tags" : [ "red", "blank", "plain" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e051"), "item" : "planner", "qty" : 75, "tags" : [ "blank", "red" ], "dim_cm" : [ 22.85, 30 ] }
</code></pre>

查询数组的一个元素

<pre><code>
rs0:PRIMARY> db.mytest.find({'tags':'red'})
{ "_id" : ObjectId("5a409a4046245769d3e9e04e"), "item" : "journal", "qty" : 25, "tags" : [ "blank", "red" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e04f"), "item" : "notebook", "qty" : 50, "tags" : [ "red", "blank" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e050"), "item" : "paper", "qty" : 100, "tags" : [ "red", "blank", "plain" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e051"), "item" : "planner", "qty" : 75, "tags" : [ "blank", "red" ], "dim_cm" : [ 22.85, 30 ] }
</code></pre>

数组的条件查询

<pre><code>
rs0:PRIMARY> db.mytest.find({'dim_cm':{$gt:25}})
{ "_id" : ObjectId("5a409a4046245769d3e9e051"), "item" : "planner", "qty" : 75, "tags" : [ "blank", "red" ], "dim_cm" : [ 22.85, 30 ] }

rs0:PRIMARY> db.mytest.find({'dim_cm':{$gt:22,$lt:25}})
{ "_id" : ObjectId("5a409a4046245769d3e9e051"), "item" : "planner", "qty" : 75, "tags" : [ "blank", "red" ], "dim_cm" : [ 22.85, 30 ] }
</code></pre>

指定元素查询
<pre><code>
rs0:PRIMARY> db.mytest.find({'dim_cm.0':{$gt:22}})
{ "_id" : ObjectId("5a409a4046245769d3e9e051"), "item" : "planner", "qty" : 75, "tags" : [ "blank", "red" ], "dim_cm" : [ 22.85, 30 ] }
</code></pre>

数组元素个数查询

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

* 数组内嵌

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

数组内嵌查询，必须按照顺序才能匹配，不按照顺序无法匹配到
<pre><code>
rs0:PRIMARY> db.mytest.find( { "instock": { warehouse: "A", qty: 5 } } )
{ "_id" : ObjectId("5a409f6446245769d3e9e053"), "item" : "journal", "instock" : [ { "warehouse" : "A", "qty" : 5 }, { "warehouse" : "C", "qty" : 15 } ] }
rs0:PRIMARY> db.mytest.find( { "instock": { qty: 5,warehouse: "A" } } )
rs0:PRIMARY>
rs0:PRIMARY>
</code></pre>

数组字段的条件查询，'.'的使用

<pre><code>
rs0:PRIMARY> db.mytest.find( { "instock.qty": {$gt:40 } } )
{ "_id" : ObjectId("5a409f6446245769d3e9e055"), "item" : "paper", "instock" : [ { "warehouse" : "A", "qty" : 60 }, { "warehouse" : "B", "qty" : 15 } ] }
</code></pre>

数组内嵌按元素查询

<pre><code>
rs0:PRIMARY> db.mytest.find( { "instock.0.qty": {$gt:40 } } )
{ "_id" : ObjectId("5a409f6446245769d3e9e055"), "item" : "paper", "instock" : [ { "warehouse" : "A", "qty" : 60 }, { "warehouse" : "B", "qty" : 15 } ] }
rs0:PRIMARY> db.mytest.find( { "instock.1.qty": {$gt:20 } } )
{ "_id" : ObjectId("5a409f6446245769d3e9e057"), "item" : "postcard", "instock" : [ { "warehouse" : "B", "qty" : 15 }, { "warehouse" : "C", "qty" : 35 } ] }
</code></pre>

多条件查询

<pre><code>
rs0:PRIMARY> db.mytest.find( { "instock.qty": 5, "instock.warehouse": "A" } )
{ "_id" : ObjectId("5a409f6446245769d3e9e053"), "item" : "journal", "instock" : [ { "warehouse" : "A", "qty" : 5 }, { "warehouse" : "C", "qty" : 15 } ] }
{ "_id" : ObjectId("5a409f6446245769d3e9e056"), "item" : "planner", "instock" : [ { "warehouse" : "A", "qty" : 40 }, { "warehouse" : "B", "qty" : 5 } ] }
</code></pre>