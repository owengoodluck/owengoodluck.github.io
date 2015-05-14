---
layout: post
title:  "iOS App  Core Data Conception"
date:   2015-05-14 22:28:49
categories: iOS-core Core Data
---

  * 1.Core Data 是数据持久化存储的最佳方式

  * 2.数据最终的存储类型可以是：SQLite数据库，XML，二进制，内存里，或自定义数据类型

在Mac OS X 10.5Leopard及以后的版本中，开发者也可以通过继承NSPersistentStore类以创建自定义的存储格式

  * 3.好处：能够合理管理内存，避免使用sql的麻烦，高效

  * 4.构成：
  
**NSManagedObjectContext**（被管理的数据上下文）
操作实际内容（操作持久层）
作用：插入数据，查询数据，删除数据

**NSManagedObjectModel**（被管理的数据模型）
数据库所有表格或数据结构，包含各实体的定义信息
作用：添加实体的属性，建立属性之间的关系
操作方法：视图编辑器，或代码

**NSPersistentStoreCoordinator**（持久化存储助理） 相当于数据库的连接器 作用：设置数据存储的名字，位置，存储方式，和存储时机

**NSManagedObject**（被管理的数据记录） 相当于数据库中的表格记录

**NSFetchRequest**（获取数据的请求） 相当于查询语句

**NSEntityDescription**（实体结构） 相当于表格结构

**.xcdatamodeld** 里面是.xcdatamodel文件，用数据模型编辑器编辑 ,编译后为.momd或.mom文件
	
---------------------------------
[iphone数据存储之－－ Core Data的使用（一）](http://www.cnblogs.com/xiaodao/archive/2012/10/08/2715477.html)

[iphone数据存储之－－ Core Data的使用（二）](http://www.cnblogs.com/xiaodao/archive/2012/10/09/2716579.html)