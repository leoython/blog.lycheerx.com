---
title: Rust学习路线
date: 2020-06-10 11:31:39
tags: rust
---

## 背景

近几个月，笔者开始学习Rust，并用Rust开始写一些代码。学到现在，不说对Rust有很深的理解，但是日常用来写一些代码是没有问题的，并且也能够根据需要进行下一步的学习。在学习的过程中，笔者也看了许多的资料，但是始终没有找到一个清晰的学习路径，可以帮助在学和写之间配合起来，所以笔者根据自己的学习经验，制作了这一份Rust的学习路径，配合一些实践和测试题，帮助大家学习Rust。同时笔者也在这里推荐一下PingCAP的[学习课程](https://university.pingcap.com/talent-plan)，其中的Rust课程质量很高，但是需要有一定的Rust基础，所以这也是笔者将其放在RoadMap最后面的原因，有经验的读者可以直接跳过前面进行

*本路线并不是最终版本，日后会根据各种资源和需求的变化进行调整*

## RoadMap One

此路线比较适合习惯先了解全貌再去实践的同学，在入门级的课程中不包括各种Rust的例子，而是旨在了解Rust的语法、语义、类型系统等，它与RoadMap Two的区别在于，学习资料的顺序是颠倒的，实际上的知识点没有区别

- 基础知识
    1. 先阅读[The Rust Reference](https://doc.rust-lang.org/reference/introduction.html)，重点了解Rust的各种语法和语义结构，有一个大概的认知
    2. 参照[Rust Language Cheat Sheet](https://cheats.rs/)，对步骤一进行总结
    3. 阅读[The Rust Programming Language](https://doc.rust-lang.org/book/title-page.html)，重点放在各种特性以及例子的实现
    4. 跟随[Rust by Example](https://doc.rust-lang.org/rust-by-example/index.html#rust-by-example)，结合步骤三进行实践
    5. 完成[本节课程](https://doc.rust-lang.org/stable/book/ch20-00-final-project-a-web-server.html)
- 测试题

    测试题没有先后区分，只要能够完成一道题就可以进行后面的学习

    - 使用Rust编写一个LinkList， 要求所有的节点需要分配在堆上，需要实现pop、push方法
    - 使用Rust编写双链双端队列以及对应的方法
- 扩展阅读

    扩展阅读部分是一些Rust的借用和所有权的一些文章，用来帮助读者了解相关知识

    - [https://blog.skylight.io/rust-means-never-having-to-close-a-socket/](https://blog.skylight.io/rust-means-never-having-to-close-a-socket/)
    - [https://blog.rust-lang.org/2015/04/10/Fearless-Concurrency.html](https://blog.rust-lang.org/2015/04/10/Fearless-Concurrency.html)
    - [https://en.wikipedia.org/wiki/Resource_acquisition_is_initialization](https://en.wikipedia.org/wiki/Resource_acquisition_is_initialization)

## RoadMap Two

此路线比较适合习惯先实践的同学，但是因为Rust与平常我们学习的语言有较大出入，我不建议直接进行实践。所以此路线还是会先进行Rust各项特性、基础的学习，但是会在学习的过程中让学习者进行实践操作，它与RoadMap One的区别是，学习资料的顺序是颠倒的，实际上的知识点没有区别

- 基础知识
    1. 阅读[The Rust Programming Language](https://doc.rust-lang.org/book/title-page.html)，重点放在各种特性以及例子的实现
    2. 阅读[The Rust Reference](https://doc.rust-lang.org/reference/introduction.html)，重点了解Rust的各种语法和语义结构，有一个大概的认知
    3. 参照[Rust Language Cheat Sheet](https://cheats.rs/)，对步骤二进行总结
    4. 跟随[Rust by Example](https://doc.rust-lang.org/rust-by-example/index.html#rust-by-example)，进行实践
    5. 完成[本节课程](https://doc.rust-lang.org/stable/book/ch20-00-final-project-a-web-server.html)

- 测试题

    测试题没有先后区分，只要能够完成一道题就可以进行后面的学习

    - 使用Rust编写一个LinkList， 要求所有的节点需要分配在堆上，需要实现pop、push方法
    - 使用Rust编写双链双端队列以及对应的方法
- 扩展阅读

    扩展阅读部分是一些Rust的借用和所有权的一些文章，用来帮助读者了解相关知识

    - [https://blog.skylight.io/rust-means-never-having-to-close-a-socket/](https://blog.skylight.io/rust-means-never-having-to-close-a-socket/)
    - [https://blog.rust-lang.org/2015/04/10/Fearless-Concurrency.html](https://blog.rust-lang.org/2015/04/10/Fearless-Concurrency.html)
    - [https://en.wikipedia.org/wiki/Resource_acquisition_is_initialization](https://en.wikipedia.org/wiki/Resource_acquisition_is_initialization)

## 进阶

完成路线一或者路线二的学习之后，可以进行进阶的学习，进阶部分不需要再学习新的资料，只需要完成两项训练即可，如有兴趣，可以再进行扩展部分的学习(强烈推荐)。

**目标**

可以使用Rust进行日常开发，熟悉Rust的各项特性、语法和语义，使用Cargo进行项目搭建，代码检测，版本发布

**内容**

[rustlings训练](https://github.com/rust-lang/rustlings)

[阅读并实践本书前6节](https://rust-unofficial.github.io/too-many-lists/)

**扩展**

扩展部分强烈建议学习，本扩展是用来学习Rust配套的[Cargo工具](https://doc.rust-lang.org/cargo/)。Cargo除了可以用作包管理外还有其他许多强大的功能可以帮助开发者开发Rust程序。

PS: 本节内容没有测试

## 最终目标

完成PingCAP[本门课程](https://university.pingcap.com/talent-plan/rust-programming)

## 额外部分，选修

- Rust异步编程，阅读[本书](https://rust-lang.github.io/async-book/01_getting_started/01_chapter.html)
- UnSafe Rust, 阅读[本书](https://doc.rust-lang.org/nomicon/index.html)
- Rust 宏， 阅读[本书](https://danielkeep.github.io/tlborm/book/index.html)
- Rust 的编程范式，[https://coolshell.cn/articles/20845.html](https://coolshell.cn/articles/20845.html)
