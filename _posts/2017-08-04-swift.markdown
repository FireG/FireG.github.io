---
layout: post
title: "Craft Beer"
date: 2016-12-5
categories:
  -blog
description: 
image: https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=3957998734,1226986245&fm=26&gp=0.jpg
image-sm: https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=4131898317,1255337817&fm=26&gp=0.jpg
---


# Swift语法糖的使用



- **语法糖的简介**
- **语法糖Selector例子**


-------------------

## 语法糖的简介

	语法糖（Syntactic sugar），也译为糖衣语法，是由英国计算机科学家彼得·约翰·兰达（Peter J. Landin）发明的一个术语，指计算机语言中添加的某种语法，这种语法对语言的功能并没有影响，但是更方便程序员使用。通常来说使用语法糖能够增加程序的可读性，从而减少程序代码出错的机会。

我个人对语法糖的理解就是让你的代码更加有逼格，别人阅读代码的时候会觉得你的代码很工整，也方便维护




### Swift 实例
 创建控制器，添加Button
``` python
  override func viewDidLoad() {
        super.viewDidLoad()
        
        let btn = UIButton(frame: CGRectMake(100,100,100,100))
        btn.backgroundColor = UIColor.redColor()
        view.addSubview(btn)
            
    }
    
    func printFire() {
        print("fire")
    }

```
想实现控制器里的Button点击事件，但是，如果一个控制器里的Button特别的多，那添加Button点击事件的Selector 会觉得特别的臃肿。所以语法糖就是要拓展Selector 

``` python
private extension Selector {
    
    static let printFire = #selector(ViewController.printFire)
    
}
```
我们现在给viewDidLoad方法中的Button 添加点击事件

```python
btn.addTarget(self, action: .printFire, forControlEvents: .TouchUpInside)
```

如果Button过多的话，用语法糖方便管理Button的点击事件，又不会把点击事件变得过于臃肿

##下面是控制器的完整代码
```python
import UIKit

class ViewController: UIViewController {

    override func viewDidLoad() {
        super.viewDidLoad()
        
        let btn = UIButton(frame: CGRectMake(100,100,100,100))
        btn.backgroundColor = UIColor.redColor()
        btn.addTarget(self, action: .printFire, forControlEvents: .TouchUpInside)
        view.addSubview(btn)
     
        
    }
    
    func printFire() {
        print("fire")
    }

    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
        // Dispose of any resources that can be recreated.
    }


}

private extension Selector {
    
    static let printFire = #selector(ViewController.printFire)
    
}


```

