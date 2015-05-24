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