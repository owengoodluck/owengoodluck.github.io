---
layout: post
title:  "Coding than Drawing"
date:   2015-05-16 22:28:49
categories: template
---

  * **Block** : AppDeligate.didFinishLaunchingWithOptions 

 {% highlight objective-C %}
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
{
    self.window = [[UIWindow alloc] initWithFrame:[[UIScreen mainScreen] bounds]];
    // Override point for customization after application launch.
    self.window.backgroundColor = [UIColor whiteColor];
    
    self.window.rootViewController = nil; // you customer view controller
    
    [self.window makeKeyAndVisible];
    return YES;
}
 {% endhighlight %} 

--------------------------------------------
  * **Block** : Create and add naviagtion bar button item
 {% highlight objective-C %}

	HYCircleLoadingView loadingView = [[HYCircleLoadingView alloc]initWithFrame:CGRectMake(0, 0, 35, 35)];
    UIBarButtonItem *loadingItem = [[UIBarButtonItem alloc]initWithCustomView:loadingView];
    self.navigationItem.leftBarButtonItem = loadingItem;

 {% endhighlight %} 


--------------------------------------------
  * **Block** : addTarget: action: forControlEvents
 {% highlight objective-C %}
    [self.startButton addTarget:self
                         action:@selector(startButtonClick:)
               forControlEvents:UIControlEventTouchUpInside];

- (void)startButtonClick:(UIButton *)button
{
    [self.loadingView startAnimation];
}
 {% endhighlight %} 

--------------------------------------------
  * **Block** : XXX
 {% highlight objective-C %}

//CODING

 {% endhighlight %} 
--------------------------------------------
  * **Block** : XXX
 {% highlight objective-C %}

//CODING

 {% endhighlight %} 
--------------------------------------------
  * **Block** : XXX
 {% highlight objective-C %}

//CODING

 {% endhighlight %} 
--------------------------------------------
  * **Block** : XXX
 {% highlight objective-C %}

//CODING

 {% endhighlight %} 
--------------------------------------------
  * **Block** : XXX
 {% highlight objective-C %}

//CODING

 {% endhighlight %} 
--------------------------------------------
  * **Block** : XXX
 {% highlight objective-C %}

//CODING

 {% endhighlight %} 
--------------------------------------------
  * **Block** : XXX
 {% highlight objective-C %}

//CODING

 {% endhighlight %} 
--------------------------------------------
  * **Block** : XXX
 {% highlight objective-C %}

//CODING

 {% endhighlight %} 
--------------------------------------------
  * **Block** : XXX
 {% highlight objective-C %}

//CODING

 {% endhighlight %} 
--------------------------------------------
  * **Block** : XXX
 {% highlight objective-C %}

//CODING

 {% endhighlight %} 
--------------------------------------------
  * **Block** : XXX
 {% highlight objective-C %}

//CODING

 {% endhighlight %} 
--------------------------------------------
  * **Block** : XXX
 {% highlight objective-C %}

//CODING

 {% endhighlight %} 
--------------------------------------------
  * **Block** : XXX
 {% highlight objective-C %}

//CODING

 {% endhighlight %} 
--------------------------------------------
  * **Block** : XXX
 {% highlight objective-C %}

//CODING

 {% endhighlight %} 
--------------------------------------------
  * **Block** : XXX
 {% highlight objective-C %}

//CODING

 {% endhighlight %} 
--------------------------------------------
  * **Block** : XXX
 {% highlight objective-C %}

//CODING

 {% endhighlight %} 
--------------------------------------------
  * **Block** : XXX
 {% highlight objective-C %}

//CODING

 {% endhighlight %} 
--------------------------------------------
  * **Block** : XXX
 {% highlight objective-C %}

//CODING

 {% endhighlight %} 
--------------------------------------------
  * **Block** : XXX
 {% highlight objective-C %}

//CODING

 {% endhighlight %} 
--------------------------------------------
  * **Block** : XXX
 {% highlight objective-C %}

//CODING

 {% endhighlight %} 
--------------------------------------------
  * **Block** : XXX
 {% highlight objective-C %}

//CODING

 {% endhighlight %} 
