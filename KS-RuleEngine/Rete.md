# Rete 算法
```md
Rete算法是Charles Forgy 在1979年的论文中首次提出的，针对基于规则知识表现的模式匹配算法。
目前来说，大部分规则引擎还是基于rete算法作为核心，但都有所改进，比如drool，jess等等。
```
```md
     (name-of-this-production
        LHS /* one or more conditions */
       -->
        RHS /* one or more actions */
       )
```
* name-of-this-production 规则
* LHS（left hand side）一系列条件
* RHS（right hand side）满足条件后应该执行的动作
