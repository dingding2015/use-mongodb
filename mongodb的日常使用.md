<h1 align="center">mongodb使用简单汇总</h1>

### 1、 mongodb需要了解的一些概念
* database 数据库 <br>

  mongodb数据库存储在data目录中 <br>
  show dbs 显示所有的数据库 <br>
  use mydb 创建和切换数据库 <br>
  
* collection 集合，数据库表，table  <br>
  集合是mongodb文档组，存储在数据库中，没有固定的结构，可以插入不同格式和类型的数据。<br>
  capped collections 固定大小的集合，有很高的性能以及队列过期的特性，需要显式创建，指定集合的大小，提前分配存储空间。<br>
  向集合插入数据，如果集合不存在则会创建集合。<br>
  
  
* document 数据记录行/文档，row <br>
  
* field 字段/域、column <br>
  
* index 索引 <br>
   
* primary key  主键，mongodb自动将_id字段设置为主键 <br>
  
  
### 2、