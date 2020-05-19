# What Is Drools

Drools是业务规则管理系统（BRMS）解决方案。  
它提供了核心业务规则引擎（BRE），Web UI和规则管理应用程序（Drools Workbench），  
对符合性级别3的决策模型和注释（DMN）模型的完整运行时支持，以及用于核心开发的Eclipse IDE插件及Idea插件。  

Drools 是一个基于Charles Forgy’s的RETE算法的，  
易于访问企业策略、易于调整以及易于管理的开源业务规则引擎，符合业内标准，速度快、效率高。   
业务分析师人员或审核人员可以利用它轻松查看业务规则，从而检验是否已编码的规则执行了所需的业务规则。

Drools是开源软件，根据Apache Software License发布。  
它用100％纯Java™编写，可以在任何JVM上运行，并且在Maven Central存储库中也可用。  

## 术语

规则
规则引擎的心脏，在其中指定条件 (如果 ‘a’ 那么 ‘b’).

概况
概况是其上的规则将在行动中的数据。从Java的角度来看，概况是POJO(普通Java对象)。

会话
    在Drools中基于知识是会话的核心部件用来触发的规则。 
    这是知识的会话保存所有的规则和其他资源。
    基于知识会话从知识库创建。

    对于规则引擎的工作，概况插入了会话，并在满足条件时，随后触发规则。
    Session有两种类型：
        无状态知识会话
        状态知识会话
议程    
这是一个逻辑概念。议程就是激活正在等待被触发的合乎逻辑的地方。

激活
激活是当时的部分规则。激活被放置在相应的规则被触发议事日程。

## KIE(Knowledge Is Everything)

KIE 是一个综合的项目，他集成了 Drools、jBPM、OptaPlanner、Drools Workbench 
以及 UberFire 五个不同但具有关联性的模块，
这些模块可以按照用户的需要组合使用从而为业务管理和自动化提供一整套解决方案。
需要通过 KIE 来操纵任意模块包括 Drools：

```java
KieServices kieServices = KieServices.Factory.get();
//获取规则引擎模块
KieContainer kContainer = kieServices.getKieClasspathContainer();
```
