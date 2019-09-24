# DRL
```md
DRL是Drools中定义的规则语言
将规则配置到xml和drl文件中，可读性较高，较为工整
```
## global
```md
通过global关键字定义的即为全局变量，全局变量不会被加入到WorkingMemory中，
因此当global变量的值发生改变时，规则引擎不会感知到，
所以，LHS中不能使用全局变量，除非是constant immutable的。
```
## accumulate
```md
Accumulate是Drools中非常强大的一个条件元素。它允许你对数据集进行操作，语法定义为：accumulate( ; [;] )
```
```md
 Drools默认支持的操作包括：average、min、max、count、sum、collectList和collectSet。
 同时，accumulate也支持UDF，只需要实现org.drools.core.runtime.rule.TypedAccumulateFunction接口即可。
```
## 规则属性
* agenda-group
```md
该属性的值是一个字符串，通过这个字符串可以将规则分为若干个组。
```
* auto-focus
```md
 属性值为true/false。
 如果为true，当对应的规则被触发时，该规则对应的agenda-group会自动获得焦点。
```
## 结构
## package

## import
## rule
```md
rule "name"
       no-loop true
       when
               $message:Message(status == 0)
       then
               System.out.println("fit");
               $message.setStatus(1);
               update($message);
end
```
### 属性部分
```md
定义当前规则执行的一些属性等，比如是否可被重复执行、过期时间、生效时间等。
```
* no-loop 
```md
定义当前的规则是否不允许多次循环执行，默认是false，也就是当前的规则只要满足条件，可以无限次执行。
```
* lock-on-active
```md
通过这个标签，可以控制当前的规则只会被执行一次，因为一个规则的重复执行不一定是本身触发的，
也可能是其他规则触发的，所以这个是no-loop的加强版。
```
* date-expires
```md
设置规则的过期时间，默认的时间格式：“日-月-年”
```
* date-effective
```md
设置规则的生效时间，时间格式同上。
```
* duration
```md
规则定时，duration 3000   3秒后执行规则
```
* salience
```md
优先级，数值越大越先执行，这个可以控制规则的执行顺序。
```
### 条件部分
```md
即LHS，定义当前规则的条件，如  when Message(); 判断当前workingMemory中是否存在Message对象。
```
```md
when：规则条件开始。条件可以单个，也可以多个，多个条件一次排列。
when
    eval(true)
    $customer:Customer()
    $message:Message(status==0)

上述罗列了三个条件，当前规则只有在这三个条件都匹配的时候才会执行RHS部分
```
* 比较操作符
```md
>  >=  <  <=  ==  !=  contains / not contains / memberOf / not memberOf /matches/ not matches
```
### 结果部分
```md
即RHS，这里可以写普通java代码，即当前规则条件满足后执行的操作，可以直接调用Fact对象的方法来操作应用。
```
```md
当规则条件满足，则进入规则结果部分执行，结果部分可以是纯Java代码
```
