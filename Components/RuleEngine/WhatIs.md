# What Is Rule Engine

规则引擎由推理引擎发展而来，是一种嵌入在应用程序中的组件，  
实现了将业务决策从应用程序代码中分离出来，并使用预定义的语义模块编写业务决策。  
接受数据输入，解释业务规则，并根据业务规则做出业务决策。  

将规则引擎想象成一个以数据和规则作为输入的系统。它将这些规则应用于数据，并根据规则定义为我们提供输出。

## Java规则引擎  

Java规则引擎起源于基于规则的专家系统，而基于规则的专家系统又是专家系统的其中一个分支。
专家系统属于人工智能的范畴，它模仿人类的推理方式，使用试探性的方法进行推理，
并使用人类能理解的术语解释和证明它的推理结论。 

推理引擎包括三部分:
模式匹配器（Pattern Matcher）
议程（Agenda）
执行引擎（Execution Engine）

推理引擎通过决定哪些规则满足事实或目标，并授予规则优先级，满足事实或目标的规则被加入议程。
模式匹配器决定选择执行哪个规则，何时执行规则；
议程管理模式匹配器挑选出来的规则的执行次序；
执行引擎负责执行规则和其他动作。 

推理引擎存在两者推理方式：演绎法（Forward-Chaining）和归纳法（Backward-Chaining）
演绎法从一个初始的事实出发，不断地应用规则得出结论（或执行指定的动作）。
归纳法则是根据假设，不断地寻找符合假设的事实。

Rete算法是目前效率最高的一个 Forward-Chaining推理算法，
许多Java规则引擎都是基于Rete算法来进行推理计算的。 

推理引擎的推理步骤如下： 
(1)将初始数据（fact）输入Working Memory。 
(2)使用Pattern Matcher比较规则库（rule base）中的规则（rule）和数据（fact）。 
(3)如果执行规则存在冲突（conflict），即同时激活了多个规则，将冲突的规则放入冲突集合。 
(4)解决冲突，将激活的规则按顺序放入Agenda。 
(5)使用执行引擎执行Agenda中的规则。重复步骤2至5，直到执行完毕所有Agenda中的规则。 

上述即是规则引擎的原始架构，Java规则引擎就是从这一原始架构演变而来的。
Drools是基于正向推理的规则引擎。
正向推理是数据驱动的，facts事实被传递到工作空间中，在那里有一个或多个规则与这些事实匹配，
并由Agenda安排执行—我们从一个事实开始，传递事实，最后得到一个结论。 

产生式规则是一个用一阶逻辑进行知识呈现的二元结构。 
when 
    
then 

Drools中的Rete算法被称为ReteOO，表示Drools为面向对象系统（Object Oriented systems）增强并优化了Rete算法。  

## 规则引擎的优点 

简化系统架构，优化应用  
提高系统的可维护性  
减少编写“硬代码”业务规则的成本和风险  
应付特殊状况，即客户一开始没有提到要将业务逻辑考虑在内  
过将规则引擎分开，它提供了更大的可重用性。  

声明式编程: 
    使用规则更加容易对复杂的问题进行表述，并得到验证 
逻辑与数据分离:
    数据保存在系统对象中，逻辑保存在规则中。
    这根本性的打破了面向对象系统中将数据和逻辑耦合起来的局面 
速度及可测量性:
    Drools的Rete、Leaps算法，提供了对系统数据对象非常有效率的匹配，这些算法经过了大量实际考验的证明 

## 何时使用 

业务逻辑经常发生改变 
代码中有很多”if””else””switch”和其它凌乱的逻辑，且总是易变的 

## 场景

流程分支非常复杂，规则变量庞大
有不确定性的需求，变更频率较高
需要快速做出响应和决策
规则变更期望脱离于开发人员，脱离coding