# JSR-94

JSR-94 是由JCP(Java Community Process)组织所制定的java规则引擎API的java请求规范。
它主要定义了规则引擎在java运行时的一些API，指导各个java规则引擎的厂商能够基于这个API实现规则引擎。

标准制定开始于14 Nov, 2000，最后于04 Aug, 2004发布当前最终版本。

当前主流支持这个标准的开源java规则引擎有：
Drools、OpenRules、JLisa、JRuleEngine。

## 目的

为了促进规则引擎技术在java程序中的发展；
增加java规则引擎厂商之间的的交流以及标准化工作；
让使用规则引擎的第三方应用更加方便与规范；
也为了简化规则引擎商对外提供的API。

## 概念
### Rule（规则）
```md
一般而言，一个规则包含两个部分：条件和操作。当条件满足时，就会执行规则定义的操作。
因为提供规则引擎的不同厂商往往规则定义的结构，规则执行的算法不同，所以JSR94标准中不直接定义规则的结构。
规则的概念表示的是一个基本单位概念，可作为一个名字或者描述。
```
### Rule Execution Set（规则执行集合）
```md
规则执行集合是指多个规则组成的集合。
JSR94也不直接定义规则集合的结构，表示的也只是一个基本单位概念。
```
### Rule Session（规则会话）
```md
Rule Session是指运行时程序与规则引擎之间的连接，一个规则会话会关联一个规则执行集合。
一个规则会话，可能会消耗规则引擎的资源，所以当程序不再使用的时候应该释放该会话资源。
```
### Stateful Rule Session（全状态规则会话）
```md
Stateful Rule Session 是指运行程序长时间的同一个规则执行集合进行交互，有记录会话时的相关状态、数据信息。
```
### Stateless Rule Session（无状态规则会话）
```md
Stateless Rule Session 提供的是一种高效、简单的API来执行规则集合，不记录会话时的相关数据信息。
```
## API

### 规则引擎运行接口

### 规则执行集合管理接口


## Reference
* [JAVA规则引擎](https://www.cnblogs.com/jzhlin/p/4255883.html)