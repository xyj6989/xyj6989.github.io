---
layout: post
title:  "dispatch_semaphore_t 的使用"
date:   2016-05-25 18:00:00 +0800
categories: iOS
tags: GCD 
---

* content
{:toc}


```objc
    dispatch_semaphore_t semaphore = dispatch_semaphore_create(0);
    dispatch_after(dispatch_time(DISPATCH_TIME_NOW, (int64_t)(second * NSEC_PER_SEC)), dispatch_get_global_queue(DISPATCH_QUEUE_PRIORITY_DEFAULT, 0), ^{
        dispatch_semaphore_signal(semaphore);
    });
    dispatch_semaphore_wait(semaphore, DISPATCH_TIME_FOREVER);
```

在使用 `dispatch_semaphore_t` 时发现，如果调用 `dispatch_semaphore_signal` 与 `dispatch_semaphore_wait`同在同一个线程时，正好信号量为0，会造成永远无法执行 `dispatch_semaphore_signal`。所以要小心使用信号量。
特此记录
