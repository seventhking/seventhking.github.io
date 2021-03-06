---
layout: post
title: "设计模式概览"
subtitle: "设计模式"
date: 2018-10-22 17:00:00
author: "Deetch"
header-img: "img/home-bg-o.jpg"
catalog: true
tags:
    - 设计模式
---

## 设计原则

1. 找出应用中可能需要变化的地方，把他们独立出来，不要和那些不需要变化的代码混在一起
2. 针对接口编程，而不是针对实现编程
3. 对用组合，少用继承
4. 为了交互对象之间的松耦合设计而努力
5. 类应该对扩展开放，对修改关闭
6. 要依赖抽象，不要依赖具体类
7. 最少知识原则：只和你的密友谈话
8. 好莱坞原则:别调用(打电话给)我们，我们会调用(打电话给)你
9. 一个类应该只有一个引起变化的原因


## 设计模式

1. 策略模式：定义了算法族，分别封装起来，让它们之间可以相互替换，此模式让算法的变化独立于使用算法的客户

2. 观察者模式：定义了对象之间的一对多依赖，这样一来，当一个对象改变状态时，它的所有依赖者都会收到通知并自动更新
3. 装饰者模式：动态的将责任附加到对象上。若要扩展功能，装饰者提供了比继承更有弹性的替代方案
4. 工厂方法模式：定义了一个由创建对象的接口，但由子类决定要实例化的类是哪一个。工厂方法让类把实例化推迟到子类
5. 抽象工厂模式：提供一个接口，用于创建相关或依赖对象的家族，而不需要明确指定具体类
6. 单例模式：确保一个类只有一个实例，并提供一个全局访问点
7. 命令模式：将“请求”封装成对象，以便使用不同的请求、队列或者日志来参数化其他对象。命令模式也支持克撤销的操作
8. 适配器模式：将一个类的接口转换成客户期望的另一个接口。适配器让原本接口不兼容的类可以合作无间。
9. 外观模式：提供了一个统一的接口，用来访问子系统中的一群接口。外观定义了一个高层接口，让子系统更容易使用
10. 模板方法模式：在一个方法中定义一个算法的骨架，而将一些步骤延迟到子类中。模板方法使得子类可以在不改变算法结构的情况下，重新定义算法中的某些步骤
11. 迭代器模式：提供一种方法顺序访问一个聚合对象中的各个元素，而又不暴露其内部的表示
12. 组合模式：允许你将对象组合成树形结构来表现“正题/部分”层次结构。组合能让客户以一致的方式处理个别对象以及对象组合
13. 状态模式：允许对象在内部状态改变时改变它的行为，对象看起来好像修改了它的类。
14. 代理模式：为另一个对象提供一个替身或占位符以控制对这个对象的访问。
