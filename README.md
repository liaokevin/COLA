# COLA
<<<<<<< HEAD
> COLA是Clean Object-oriented & Layered Architecture的缩写，是轻量级的企业应用框架，可以有效的降低业务系统复杂度。
![image.png](http://ata2-img.cn-hangzhou.img-pub.aliyun-inc.com/26321403c9123efc269cb6013c55555f.png)
=======
> COLA是Clean Object-Oriented and Layered Architecture的缩写，代表“整洁面向对象分层架构”，也叫“可乐”架构。
>>>>>>> 4cc8105518388c16e8d102b2d3ff74de70d0f92e

关于架构和设计的详细内容，请查看：https://www.atatech.org/articles/96063

# 项目说明
COLA框架包括两个Project，一个是cola-framework里面是框架的核心代码，另一个是cola-archetype是用来生成新应用的Maven Archetype源码。
## cola-framework Project
该Project包含3个Module，cola-core, cola-common, cola-test
### cola-core
该Module是整个框架的核心，里面的主要功能和Package如下：
```
com
└── alibaba
    └── cola
        ├── assembler  \\提供Assembler标准
        ├── boot \\这是框架的核心启动包，负责框架组件的注册、发现
        ├── command  \\提供Command标准
        ├── common
        ├── context  \\提供框架执行所需要的上下文
        ├── convertor  \\提供Convertor标准
        ├── domain  \\提供Domain Entity标准
        ├── event
        ├── exception \\提供Exception标准
        ├── extension  \\负责扩展机制中的重要概念-扩展(Extension)的定义和执行
        ├── extensionpoint  \\负责扩展机制中的重要概念-扩展点(Extension Point)的定义
        ├── logger  \\提供DIP的日志接口
        ├── repository  \\提供仓储（Repository）的标准
        ├── rule  \\提供业务规则或者叫策略（Rule）的标准和执行
        │   └── ruleengine
        └── validator  \\提供Validator标准和执行
```
### cola-common
该Module提供了框架中Client Object, Entity Object和Data Object的定义，二方库会依赖该Module。
### cola-test  
该Module主要是提供一些开发测试的工具，可以使用TDD来进行开发。

## cola-archetype Project
该Project下面是Archetype的源码，先执行`mvn install`，然后就可以用下面的命令来创建新应用了：
```
mvn archetype:generate  -DgroupId=com.alibaba.demo -DartifactId=sample -Dversion=1.0.0-SNAPSHOT -Dpackage=com.alibaba.demo -DarchetypeArtifactId=cola-framework-archetype -DarchetypeGroupId=com.alibaba.cola -DarchetypeVersion=1.0.0-SNAPSHOT
```
生成的应用主要包括demo-app, demo-domain, demo-tunnel, demo-config, demo-client和Start五个Module，分别代表不同层次（layer）和用途。