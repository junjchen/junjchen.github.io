---
layout: post
title:  "之前后台存在的问题"
categories: joker
---

### 代码

- 代码是根据一个其他项目修改的，存在大量冗余代码，可维护性差 ![其他项目代码](/assets/joker/copied-codes.png)

- 代码格式无规范，有许多代码块重复，异常没有处理 ![重复代码](/assets/joker/repetitive-codes.png)

- DAO层实现没有使用ORM框架，而是使用jdbcTemplate搞定CRUD，极难维护（以及图中重复代码） ![没有ORM](/assets/joker/no-orm.png)

### 数据库

- 命名无规范（图中其实是游戏的数据表） ![命名无规范](/assets/joker/db-naming.png)

- 由于Sinaapp欠费无法看到数据库，但我怀疑有许多不相关数据都存在数据库中（指那个其他项目的数据）

- 没有仔细看遍sql，不过似乎外键和index都无定义（图中AUTHOR应定义与作者表相连的外键） ![数据表定义](/assets/joker/db-foreign-key.png)

- 数据表结构混乱，扩展困难

### 传输

- HTTP传输明文账号密码，不安全

### 接口定义

- 接口不完整（目前定义的所有借口，明显不足） ![所有接口](/assets/joker/all-apis.png)