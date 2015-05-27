---
layout: post
title:  "Code Snippet"
date:   2015-05-01 22:28:49
categories: Core
---

## Get application delegatte
 {% highlight objective-C %}
	AppDelegate *appDelegete = ((AppDelegate *)([[UIApplication sharedApplication] delegate]));
 {% endhighlight %} 

 --------------------------------------------

## Prevent navigation/tabBar overlap embeded  view  
add below code in embeded view when did load ,availabe for ios7 and later
 {% highlight objective-C %}
	
    if([[[UIDevice currentDevice] systemVersion] floatValue] >= 7.0){
        self.edgesForExtendedLayout = UIRectEdgeNone;
        self.automaticallyAdjustsScrollViewInsets = NO;
    }

 {% endhighlight %} 

Hide tabBar ` detailVC.hidesBottomBarWhenPushed = YES; `
 --------------------------------------------

## DateFormat
 {% highlight objective-C %}
        NSDateFormatter *dateFormat = [NSDateFormatter new];
        [dateFormat setDateFormat:@"MM.dd HH:mm"];
        NSString *dateString = [dateFormat stringFromDate:self.article.date];
 {% endhighlight %} 

  --------------------------------------------

## Toolbar and bar button usage
ToolBar、Bar Button Item、Fixed Space Bar Button Item、Flexible Space Bar Button Item。前两个是可见的工具栏和工具栏项目，后两个只是用于调节按钮位置固定调节和灵活调节。  
By default , if we just add bar button items into tool bar ,then the items will be arranged from left to right one by one .    
if you add some space between 2 items , then for Fixed Space Bar Button Item, it will only take certain space . for Flexible Space Bar Button Item, it will try to occupy as many space as possible .     
if you have 2 bar buttons and you want to put then on 2 side of the toolbar ,then you can add a  Fixed Space Bar Button Item between them.  
if you have 3 bar bottons and you want then in left center and right , then you need to add 2 Fixed Space Bar Button Items  insides them  