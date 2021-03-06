## 简介
本项目是一个c++编写的多线程Web服务器，使用了Reactor并发模型，非阻塞I/O；支持http get请求。

## 特点

- 基于事件驱动，使用`Reactor`模式 + `EPOLL`I/O多路复用。
- 支持多线程模式，每个线程维护一个事件循环（`eventloop`）。
- 使用`unique_ptr`,`shared_ptr`等智能指针控制对象生命周期。
- 使用`function`+`bind/lambda`完成回调。
- 使用了`eventfd`实现了线程的唤醒。
- 用`Webbench` 对服务器进行压测。

## 测试
**环境**：  
    i5-4210M双核处理器，8G内存，ubuntu16.04系统

**结果**:  
单线程下：  
![Webserver](https://github.com/hzhzhhz/Webserver/blob/master/pic/single_web.png) ![Muduo](https://github.com/hzhzhhz/Webserver/blob/master/pic/single_muduo.png)  
多线程下(4线程)：  
![Webserver](https://github.com/hzhzhhz/Webserver/blob/master/pic/multi_web.png)![Muduo](https://github.com/hzhzhhz/Webserver/blob/master/pic/multi_muduo.png)
## todo
- 实现定时器
- 实现日志系统

## 参考

Muduo https://github.com/chenshuo/muduo
