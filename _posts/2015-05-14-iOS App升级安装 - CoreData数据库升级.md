---
layout: post
title:  "iOS App升级安装 - CoreData数据库升级"
date:   2015-05-14 22:28:49
categories: iOS-core Core Data
---

如果IOS App 使用到CoreData，并且在上一个版本上有数据库更新（新增表、字段等操作），那在覆盖安装程序时就要进行CoreData数据库的迁移，具体操作如下：

  1.选中你的mydata.xcdatamodeld文件，选择菜单editor->Add Model Version  比如取名：mydata2.xcdatamodel

  2.设置当前版本
   选择上级mydata.xcdatamodeld ，在inspector中的Versioned Core Data Model选择Current模版为mydata2

  3.修改新数据模型mydata2，在新的文件上添加字段及表

  4.删除原来的类文件，重新生成下类。

 {% highlight objective-C %}
	
- (NSPersistentStoreCoordinator *)persistentStoreCoordinator {
    if (_persistentStoreCoordinator != nil) {
        return _persistentStoreCoordinator;
    }
    NSURL *storeUrl = [NSURL fileURLWithPath: [[self applicationDocumentsDirectory]
                                               stringByAppendingPathComponent: @"RSS.sqlite"]];
    NSError *error = nil;

    NSDictionary *options = [NSDictionary dictionaryWithObjectsAndKeys:
                             [NSNumber numberWithBool:YES], NSMigratePersistentStoresAutomaticallyOption,
                             [NSNumber numberWithBool:YES], NSInferMappingModelAutomaticallyOption, 
                             nil];
    _persistentStoreCoordinator = [[NSPersistentStoreCoordinator alloc]
                                   initWithManagedObjectModel:[self managedObjectModel]];
    if(![_persistentStoreCoordinator addPersistentStoreWithType:NSSQLiteStoreType
                                                  configuration:nil
                                                            URL:storeUrl
                                                        options:options
                                                          error:&error]) {
        /*Error for store creation should be handled in here*/
    }
    return _persistentStoreCoordinator;
}

 {% endhighlight %} 

