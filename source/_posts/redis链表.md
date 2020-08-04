---
title: redis链表
date: 2020-08-04 10:05:09
tags:
---
redis的链表是双向链表，提供了高效的节点重排能力和顺序访问能力并且可以通过增删节点来调整列表长度

## redis链表结构

### Node结构

```c
typedef struct listNode{
	// 前驱节点
	struct listNode *prev;
	// 后置节点
	struct listNode *next;
	// 节点存储的值
	void *value;
}
```

### list结构

```c
typedef struct list{
	// 表头节点
	listNode *head;
	// 表尾节点
	listNode *tail;
	// 列表包含的节点数量
	unsigned long len;
	// 节点值复制函数
	void *(*dup) (void *ptr)
	// 节点值释放函数
	void *(*free) (void *ptr)
	// 节点值比较函数
	void *(*match) (void *ptr, void *key)
}
```

### redis链表特性

- 双端，获取某个节点的前驱和后继节点的复杂度都是O(1)
- 无环，表头的前驱和表尾的后继节点都指向NULL，遍历以NULL为结束
- 带表头指针和表尾指针
- 带链表长度计数器，获取链表长度的复杂度是O(1)
- 多态，可以用来存储不同类型的值

## Q&A

### redis链表通常用来实现什么功能？

- 列表
- 订阅发布
- 慢查询
- 监视器

### redis链表有什么特性？

- 无环
- 双端
- 可以用来保存各种类型的数据

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/fcee271d-f039-41f6-b3ab-9e13ef0b893b/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/fcee271d-f039-41f6-b3ab-9e13ef0b893b/Untitled.png)