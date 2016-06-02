---
layout: post
title:  "UILabel与YYLabel的对比测试"
date:   2016-06-02 16:00:00 +0800
categories: iOS
tags: UIKit 
---

#UILabel与YYLabel的对比测试

最近一直使用YYKit框架，觉得非常好用，但是在同时使用Autolayout时，发现了YYLabel在自动布局下面的一些缺陷。如下图：

![示例图片]({{ site.url }}/assets/UILabel与YYLabel的对比测试_1.png)

源代码部分为：

```Objective-C
    NSString *testString = @"这个是很长的测试字符串这个是很长的测试字符串这个是很长的测试字符串这个是很长的测试字符串\n这个是很长的测试字符串这个是很长的测试字符串这个是很长的测试字符串这个是很长的测试字符串这个是很长的测试字符串";
    
    UILabel *uiLabel = [[UILabel alloc] initWithFrame:CGRectZero];
    uiLabel.numberOfLines = 0;
    uiLabel.text = testString;
    uiLabel.backgroundColor = [UIColor redColor];
    [self.view addSubview:uiLabel];
    
    [uiLabel mas_makeConstraints:^(MASConstraintMaker *make) {
        make.left.mas_equalTo(self.view).offset(30);
        make.right.mas_equalTo(self.view).offset(-30);
        make.top.mas_equalTo(self.view).offset(80);
    }];
    
    YYLabel *yyLabel = [[YYLabel alloc] initWithFrame:CGRectZero];
    yyLabel.numberOfLines = 0;
    yyLabel.text = testString;
    yyLabel.backgroundColor = [UIColor blueColor];
    [self.view addSubview:yyLabel];
    
    [yyLabel mas_makeConstraints:^(MASConstraintMaker *make) {
        make.left.mas_equalTo(self.view).offset(30);
        make.right.mas_equalTo(self.view).offset(-30);
        make.top.mas_equalTo(self.view).offset(280);
    }];
```

YYLabel在自动布局支持方面还有不足，但是YYKit确实很赞。

