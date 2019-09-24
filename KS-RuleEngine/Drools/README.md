# [Drools](https://github.com/kiegroup/drools)

* [Drools Documentation](https://docs.jboss.org/drools/release/7.26.0.Final/drools-docs/html_single/index.html)
* [Drools 中文文档](http://ksoong.org/drools-examples/content/)

## [WhatIs](WhatIs.md)

## 规则文件 
## 动态生成规则
```md
更为灵活
```
### 编译与运行
```md
规则的编译与运行要通过Drools 提供的各种API 来实现，
这些API 总体来讲可以分为三类：规则编译、规则收集和规则的执行。
```

## Fact 对象
```md
在Drools 当中是通过向WorkingMemory中插入 Fact 对象的方式来实现规则引擎与业务数据的交互，
对于Fact对象就是普通的JavaBean对象。
```
```md
Drools除了可以接受用户在外部向WorkingMemory当中插入现成的Fact对象，
还允许用户在规则文件当中定义一个新的Fact 对象, 在规则文件当中定义Fact 对象要以declare 关键字开头，
以end 关键字结尾，中间部分就是该Fact 对象的属性名及其类型等信息的声明。
```
## WorkingMemory
```md
装载规则 和 Fact 对象，进行运算。
Drools5 当中提供了两个对象与规则引擎进行交互：StatefulKnowledgeSession和StatelessKnowledgeSession。
```

## 组件
### DroolsExpert 规则引擎
#### 规则语法
* [DRL(Drools Rule Language)](DRL.md)
* [DSL(Domain Specific Language)](DSL.md)
* Decision Table
* Rule Flow

### DroolsFusion  CEP复杂事件处理
### DroolsFlow 工作流，结合规则与工作流
### DroolsGuvnor 业务规则管理系统（BRMS）

## API
### 规则编译
### 规则收集
### 规则执行

## 性能
```md
Drools主要分为两个场景，一个是规则预编译，一个是规则匹配，这两个地方是性能瓶颈点。
```
```md
目前Drools都是通过文件流把规则加载到内存中，频率是100ms，1s，1min。
发现每次加载4核cpu差不多130%，即单核cpu 30%-40%，
如果针对规则变更很频繁的需求，用这种方式加载是无法满足需求的。
```
```md
6.5.0.Final、7.2.0.Final在预编译加载规则并不能带来性能提升，匹配也没有性能瓶颈
```

## 版本
```md
Drools是从6.4.0开始支持JDK8
7.2.0版本增加了多线程规则引擎和OOPath改进
```

## [Drools Code Demo](https://github.com/SunnnyChan/JavaDemo/tree/master/demo-cookbook/src/main/java/me/sunny/demo/cookbook/drools)
