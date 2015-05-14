---
layout: post
title:  "NSFileManager URLsForDirectory"
date:   2015-05-10 22:28:49
categories: iOS-core
---

# Correct codeing
 {% highlight objective-C %}
-(NSURL *)uniqueDoucmentionURL{
   	NSArray * documentDirectories  = [[NSFileManager defaultManager] URLsForDirectory:NSDocumentDirectory inDomains:NSUserDomainMask];
	NSString * unique = [NSString stringWithFormat:@"%.0f",floor([NSDate timeIntervalSinceReferenceDate])];
	return [[documentDirectories lastObject] URLByAppendingPathComponent:unique];
}
 {% endhighlight %} 

# Wrong coding
{% highlight objective-C %}
	-(NSURL *)uniqueDoucmentionURL{
		NSArray * documentDirectories  = [[NSFileManager defaultManager] URLsForDirectory:NSDocumentationDirectory inDomains:NSUserDomainMask];
		NSString * unique = [NSString stringWithFormat:@"%.0f",floor([NSDate timeIntervalSinceReferenceDate])];
		return [[documentDirectories lastObject] URLByAppendingPathComponent:unique];
	}
{% endhighlight %}

The difference is that the correct code snip is using **NSDocumentDirectory** as parameter but the wrong code snip is using **NSDocumentationDirectory** .


------------------------------
# Another way to get the directory :

{% highlight objective-C %}
	NSString *rootPathString = [NSSearchPathForDirectoriesInDomains(NSDocumentDirectory, NSUserDomainMask, YES) lastObject];
	NSURL *storeUrl =[ NSURL fileURLWithPath: [rootPathString stringByAppendingPathComponent: @"RSS.sqlite"] ];
{% endhighlight %}
