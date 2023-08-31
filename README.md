# Todo List 备忘录

**此项目使用`Gin`+`Gorm` ，基于`RESTful API`实现的一个备忘录**。

## 项目运行

**本项目使用`Go Mod`管理依赖。**

将所有环境拉取启动

```shell
make env-up
```

**下载依赖**

```shell
go mod tidy
```

**运行**

```shell
go run ./cmd/main.go
```

将所有环境关闭并删除

```shell
make env-down
```

# 接口文档

访问 http://localhost:3000/swagger/index.html 

查看**swagger**文档

## 项目主要功能介绍

- 用户注册登录 ( jwt-go鉴权 )
- 新增/删除/修改/查询 备忘录
- 存储每条备忘录的浏览次数
- 分页功能

## 项目主要依赖：

**Golang V1.15**

- Gin
- Gorm
- mysql
- redis
- ini
- jwt-go
- logrus
- go-swagger

## 项目结构

```shell
TodoList/
├── api
├── cmd
├── conf
├── consts
├── docs
├── middleware
├── pkg
│  ├── e
│  └── util
├── routes
├── repository
│  ├── cache
│  └── db
│     ├── dao
│     └── model
├── routes
├── service
└── types
```

- api : 用于定义接口函数,也就是controller层
- cmd : 程序启动
- conf : 用于存储配置文件
- middleware : 应用中间件
- pkg/e : 封装错误码
- pkg/logging : 日志打印
- pkg/util : 工具函数
- repository: 仓库放置所有存储
- repository/cache: 放置redis缓存
- repository/db: 持久层MySQL仓库
- repository/db/dao: 对db进行操作的dao层
- repository/db/model: 定义所有持久层数据库表结构的model层
- routes : 路由逻辑处理
- service : 接口函数的实现
- types : 放置所有的定义的结构体
