# 什么是中间件？

顾名思义，中间件处于操作系统软件与用户的应用软件的中间。
中间件在操作系统、网络和数据库之上， 应用软件的下层，总的作用是为处于自己上层的应用软件提供运行与开发的环境，帮助用户灵活、高效地开发和集成复杂的应用软件。

目前，它并没有很严格的定义，但是普遍接受IDC的定义：  
中间件是一种独立的系统软件服务程序，分布式应用软件借助这种软件在不同的技术之间共享资源，  
中间件位于客户机服务器的操作系统之上，管理计算资源和网络通信。  

从这个意义上可以用一个等式来表示中间件：中间件=平台+通信，  
这也就限定了只有用于分布式系统中才能叫中间件，同时也把它与支撑软件和实用软件区分开来。  

中间件是在操作系统功能范围外为应用提供服务的多用途软件。任何位于内核和用户应用之间的软件都可以是中间件。  
中间件不提供传统应用的功能，而是将软件与其他软件衔接。  
由于中间件能够让数据从一个应用流动到另一个中，因此把它比作输水管最为贴切。

中间件就是程序中可织入的，可重用的，与业务逻辑无关的各种组件。
中间件(middleware)是基础软件的一大类，属于可复用软件的范畴。

中间件实质上充当隐藏转换层，实现了分布式应用程序的通信和数据管理。
它有时被称为管道，因为它将两个应用程序连接在一起，使数据和数据库可在“管道”间轻松传递。

所谓的「中间」是相对于架构体系内的，它不涉及具体的业务逻辑也不涉及底层的硬件逻辑，  
用于用户数据交换和管理，能够起到「中介」的作用，这就是中间件。

中间件在现代信息技术应用框架如Web服务、面向服务的体系结构等中应用比较广泛。

## 基本功能

中间件是独立的系统级软件，连接操作系统层和应用程序层，将不同操作系统提供应用的接口标准化，协议统一化，屏蔽具体操作的细节。

* 通信支持
* 应用支持
* 公共服务
