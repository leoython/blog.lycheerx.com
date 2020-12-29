---
title: 使用pprof 分析go web应用的性能
date: 2020-12-29 18:17:45
tags:
---
## 背景

前段时间对手上的项目做了一些性能优化，项目大多都是Node和Go, Go的项目主要是使用 pprof 来做性能分析，这里主要就是想记录一下一些命令的用法和概念避免遗忘

## 使用

因为我的项目主要是一些web应用，所以可以直接在 main.go 中导入 pprof 使用

```
package main

import (
	"log"
	"net/http"
	_ "net/http/pprof"
	"os"
	"runtime"
	"time"

	"github.com/leoython/go-pprof-demo/dog"
)

func main() {
	log.SetFlags(log.Lshortfile | log.LstdFlags)
	log.SetOutput(os.Stdout)

	runtime.GOMAXPROCS(1)
	runtime.SetMutexProfileFraction(1)
	runtime.SetBlockProfileRate(1)

	go func() {
		if err := http.ListenAndServe(":8000", nil); err != nil {
			log.Fatal(err)
		}
		os.Exit(0)
	}()

	for {
		for _, v := range dog.Dog {
			v.Live()
		}
		time.Sleep(time.Second)
	}
}
```

## 一些概念

### flat

Sort entries based on own weight.

可以理解为函数本身的weight，在不同的pprof命令下语义是不一样，例如分析cpu占用的时候是cpu占用时间，分析内存占用的时候是内存大小

需要注意的是这个值是不包括函数调用，即等待子函数时产生的数据的

### cum

它和flat的含义其实差不多，唯一的区别是cum包含函数调用的数据，即等待子函数时产生的数据

## 一些命令

##### 分析cpu占用

go tool pprof http://localhost:6060/debug/pprof/profile

##### 分析内存泄露

go tool pprof http://localhost:6060/debug/pprof/heap

##### 分析内存分配/GC问题

go tool pprof http://localhost:6060/debug/pprof/allocs

##### 分析 goroutine 泄露

go tool pprof http://localhost:6060/debug/pprof/goroutine

##### 分析锁

go tool pprof http://localhost:6060/debug/pprof/mutex

##### 分析阻塞

go tool pprof http://localhost:8000/debug/pprof/block

## PS

如果要生成图表的话需要安装 graphviz

