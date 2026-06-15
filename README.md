# TinyPHP Framework 1.0

## 中文

### 简介

一款经过生产环境检验（日 PV 十亿级）的轻量级 PHP 框架，v1.0.1 版本，高性能毫秒级响应。

```shell
# 支持 Web 和 Console 两种模式，单文件入口，自动识别 Web / CLI 环境
php index.php
```

支持 Console 环境下的 Daemon 守护进程模式（主要适用于 Linux CentOS 7）：

```shell
# 实现经典的 Master-Worker 模式
php index.php --id=tinyphp-daemon --daemon=start

# 可扩展为 TCP 服务端程序、定时器、IO 异步事件驱动等，365x24 稳定运行
```

支持一键打包成单文件可执行程序：

```shell
# 编译
php index.php --build

# 运行生成的 phar 单文件程序
php tinyphp-demo.phar
```

### 框架安装

```shell
git clone https://github.com/aigmlab/tinyphp.git
cd tinyphp

# 兼容 Composer 安装
composer install aigm/tinyphp-framework-1.0 @dev

# 直接 Git 下载
mkdir lib/ && cd lib
git clone https://github.com/aigmlab/tinyphp.git

# 运行
php index.php

# 编译
php index.php --build

# 开启守护进程
php index.php -d

# 编辑配置文件
vi application/config/profile.php
```

### 一键搭建 LNMP 运行环境

#### lnmp-utils

Linux (CentOS 7 X64) + OpenResty (Nginx) + MySQL + PHP + Redis 一键安装包。

项目地址: [https://github.com/aigmlab/lnmp-utils](https://github.com/aigmlab/lnmp-utils)

#### CentOS 7 X86_64 (生产环境)

```shell
git clone https://github.com/aigmlab/lnmp-utils.git
cd ./lnmp-utils
./install.sh -m lnmp
curl http://127.0.0.1
```

### 框架开发规范

#### 一、PHP 编码规范

- [第一章 文件结构](https://github.com/aigmlab/tinyphp-framework-1.0/blob/master/docs/001-%E7%BC%96%E7%A0%81%E8%A7%84%E8%8C%83/001%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84.md)
- [第二章 程序的排版](https://github.com/aigmlab/tinyphp-framework-1.0/blob/master/docs/001-%E7%BC%96%E7%A0%81%E8%A7%84%E8%8C%83/002%E7%A8%8B%E5%BA%8F%E7%9A%84%E6%8E%92%E7%89%88.md)
- [第三章 命名规则](https://github.com/aigmlab/tinyphp-framework-1.0/blob/master/docs/001-%E7%BC%96%E7%A0%81%E8%A7%84%E8%8C%83/003%E5%91%BD%E5%90%8D%E8%A7%84%E5%88%99.md)
- [第四章 表达式和基本语句](https://github.com/aigmlab/tinyphp-framework-1.0/blob/master/docs/001-%E7%BC%96%E7%A0%81%E8%A7%84%E8%8C%83/004%E8%A1%A8%E8%BE%BE%E5%BC%8F%E5%92%8C%E5%9F%BA%E6%9C%AC%E8%AF%AD%E5%8F%A5.md)
- [第五章 常量](https://github.com/aigmlab/tinyphp-framework-1.0/blob/master/docs/001-%E7%BC%96%E7%A0%81%E8%A7%84%E8%8C%83/005%E5%B8%B8%E9%87%8F.md)
- [第六章 函数设计](https://github.com/aigmlab/tinyphp-framework-1.0/blob/master/docs/001-%E7%BC%96%E7%A0%81%E8%A7%84%E8%8C%83/006%E5%87%BD%E6%95%B0%E8%AE%BE%E8%AE%A1.md)
- [第七章 IDE 的选择](https://github.com/aigmlab/tinyphp-framework-1.0/blob/master/docs/001-%E7%BC%96%E7%A0%81%E8%A7%84%E8%8C%83/007IDE%E7%9A%84%E9%80%89%E6%8B%A9.md)
- [第八章 编码规范示例](https://github.com/aigmlab/tinyphp-framework-1.0/blob/master/docs/001-%E7%BC%96%E7%A0%81%E8%A7%84%E8%8C%83/008%E7%BC%96%E7%A0%81%E8%A7%84%E8%8C%83%E7%9A%84%E4%B8%80%E4%BA%9B%E7%A4%BA%E4%BE%8B.md)

#### 二、SQL 使用规范

- [第一章 查询规范](https://github.com/aigmlab/tinyphp-framework-1.0/blob/master/docs/002-SQL%E8%A7%84%E8%8C%83/001%E6%9F%A5%E8%AF%A2%E8%AF%AD%E5%8F%A5.md)
- [第二章 库和表的规范](https://github.com/aigmlab/tinyphp-framework-1.0/blob/master/docs/002-SQL%E8%A7%84%E8%8C%83/002%E5%BA%93%E5%92%8C%E8%A1%A8%E7%9A%84%E8%A7%84%E8%8C%83.md)
- [第三章 数据库设计原则](https://github.com/aigmlab/tinyphp-framework-1.0/blob/master/docs/002-SQL%E8%A7%84%E8%8C%83/003%E6%95%B0%E6%8D%AE%E5%BA%93%E8%AE%BE%E8%AE%A1%E5%8E%9F%E5%88%99.md)
- [第四章 数据库优化原则](https://github.com/aigmlab/tinyphp-framework-1.0/blob/master/docs/002-SQL%E8%A7%84%E8%8C%83/004%E6%95%B0%E6%8D%AE%E5%BA%93%E4%BC%98%E5%8C%96%E5%8E%9F%E5%88%99.md)

#### 三、框架使用手册

- [第一章 框架入门](https://github.com/aigmlab/tinyphp-framework-1.0/blob/master/manual/001%E6%A1%86%E6%9E%B6%E5%85%A5%E9%97%A8.md)

---

## English

### Overview

A production-tested (1+ billion daily PV), lightweight PHP framework — v1.0.1, high-performance with millisecond response times.

```shell
# Supports both Web and Console modes via a single entry point
php index.php
```

Daemon mode for Console environments (primarily Linux CentOS 7):

```shell
# Classic Master-Worker pattern
php index.php --id=tinyphp-daemon --daemon=start

# Extensible to TCP servers, timers, async IO event-driven modes — 365x24 stable
```

Single-file executable packaging:

```shell
# Build
php index.php --build

# Run the generated phar executable
php tinyphp-demo.phar
```

### Installation

```shell
git clone https://github.com/aigmlab/tinyphp.git
cd tinyphp

# Composer install
composer install aigm/tinyphp-framework-1.0 @dev

# Or direct Git clone
mkdir lib/ && cd lib
git clone https://github.com/aigmlab/tinyphp.git

# Run
php index.php

# Build
php index.php --build

# Start daemon
php index.php -d

# Edit config
vi application/config/profile.php
```

### LNMP Environment Setup

#### lnmp-utils

Linux (CentOS 7 X64) + OpenResty (Nginx) + MySQL + PHP + Redis one-click installer.

Repository: [https://github.com/aigmlab/lnmp-utils](https://github.com/aigmlab/lnmp-utils)

#### CentOS 7 X86_64 (Production)

```shell
git clone https://github.com/aigmlab/lnmp-utils.git
cd ./lnmp-utils
./install.sh -m lnmp
curl http://127.0.0.1
```

### Coding Standards

The framework includes comprehensive documentation covering:

- PHP coding standards (file structure, formatting, naming, expressions, constants, function design)
- SQL usage guidelines (query standards, table/database conventions, design and optimization principles)
- Framework manual and getting-started guide

See the [中文](#中文) section above for the complete document index.
