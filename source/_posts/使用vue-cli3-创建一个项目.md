---
title: 使用vue-cli3 创建一个项目
categories: 框架
date: 2019-10-02 21:39:48
tags: vue
---

从头构建一个vue2.x项目（1）

[vue-cli3](https://cli.vuejs.org/zh/) 是官方脚手架工具。下面介绍如何用它生成一个项目。

## 安装 vue-cli3

```bash
npm install -g @vue/cli
```

检查是否安装正确：

```bash
vue --version
```

## 使用图形化界面创建项目

```bash
vue ui
```

打开 `http://localhost:8000`，（点击左下角图标回到首页，）点击**创建**。

### 详情

1. 命名：vue2-demo
2. 包管理器：npm（相比新版本npm，yarn的优势已不明显）
3. 初始化 git 仓库：feat: 初始化vue2 demo项目

### 预设

1. 选择**手动**

### 功能

1. Babel: 开
2. Typescript: 关（vue3才和ts更好的搭配）
3. PWA: 开
4. Router: 开
5. Vuex: 开
6. CSS Pre-processors: 开
7. Liner/Formatter: 开
8. Unit Testing: 开
9. E2E Testing: 开
10. 使用配置文件: 开（使package.json行数不那么多）

### 配置

1. Use history mode for router: 开
2. Pick a CSS pre-processor: SCSS(with dart-sass) 官方主推 dart-sass
3. Pick a linter/formatter config: ESLint + Airbnb config（稍后再配置prettier）
4. Pick additional lint features:
	- Lint on save: 开
	- Lint and fix on commit: 关（手动fix，避免自动fix产生奇怪的问题）
5. Pick a unit testing solution: Jest（简单时尚）
6. Pick a E2E testing solution: Cypress(Chrome only) (简单时尚)

### 创建

选择**保存预设并创建项目**

### 跑起来看一下

1. 点击侧边栏最后一个**任务**图标
2. 点击 **serve**
3. 点击右侧的**运行**
4. 浏览器打开 `http://localhost:8080`

至此，项目就完成创建啦。