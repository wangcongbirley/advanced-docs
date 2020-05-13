*Github用户如果访问速度慢的话，点击[在线阅读](https://wangcongbirley.gitee.io/sjg/)*

<p align="center">
<a href="https://github.com/wangcongbirley/Senior-Java-Guide" target="_blank">
	<img src="./images/logo.png" width="20%" />
</a>
</p>

<p align="center">
  <a href=""><img src="https://img.shields.io/badge/阅读-read-brightgreen.svg" alt="阅读"></a>
  <a href="#投稿"><img src="https://img.shields.io/badge/support-投稿-critical.svg" alt="投稿"></a>
</p>


## 目录
- [系统设计](#系统设计)
    - [系统整体设计](#系统整体设计)
    - [框架篇](#框架篇)
        - [Spring](#spring)
        - [SpringBoot](#springboot)
        - [SpringMVC](#springmvc)
        - [MyBatis](#mybatis)
    - [微服务](#微服务)
       - [项目架构](#项目架构)
       - [技术栈选型](#技术栈选型)
       - [网关层](#网关层)
       - [注册中心](#注册中心)
       - [nacos](#nacos)  
       - [治理策略](#治理策略)
       - [运维服务层](#运维服务层)
       - [系统监控](#系统监控)    
       - [部署](#部署)
           - [Docker](#Docker)
           - [tomcat集群](#tomcat集群)
    - [消息队列](#消息队列)
    - [分布式](#分布式)
        - [Elasticsearch](#elasticsearch)
        - [消息队列](#消息队列)
        - [API 网关](#api-网关)
        - [唯一 id 生成](#唯一-id-生成)
        - [数据库扩展](#数据库扩展)
    - [高并发](#大型网站架构)
        - [高并发](#高并发)
        - [高可用](#高可用)
- [工具篇](#工具篇)
    - [Linux](#linux)
    - [Docker](#docker)
    - [Maven](#maven)
- [其他](#其他)
    - [jvm原理](#jvm原理)
    - [java并发](#并发)
- [说明](#说明)
    - [Senior-Java-Guide介绍](#seniorjavaguide介绍)
    - [作者的其他开源项目推荐](#作者的其他开源项目推荐)
    - [关于转载](#关于转载)
    - [如何对该开源文档进行贡献](#如何对该开源文档进行贡献)
    - [为什么要做这个开源文档？](#为什么要做这个开源文档)
    - [投稿](#投稿)
    - [联系我](#联系我)

## 系统设计

#### 系统整体设计

- [系统架构方案](docs/microservice/systemdesign.md)

### 框架篇

#### Spring

1. [Spring 学习与面试](docs/spring/spring.md)

2. [Spring AOP介绍](docs/spring/springaop.md)

#### SpringBoot

- [SpringBoot 指南](docs/microservice/springboot.md)

- [SpringBoot启动原理分析](docs/microservice/springboot-starter.md)

- [Spring 所有注解及使用方法](docs/microservice/springannotation.md)


#### SpringMVC
- [SpringMVC 工作原理详解](docs/spring/springmvc.md)

#### MyBatis

- [MyBatis常见问题总结](docs/orm/mybatis.md)

### 微服务

自顶向下设计微服务平台，以下是系统设计过程。

### 项目架构
系统分层，用户、接入层、网关层、业务服务层、基础服务层、运维服务层。分层目的是松耦合，增加拓展性。架构图如下
![](/images/1.png)

前端使用vue/element-ui构建可视界面，后端采用maven多模块/springboot构建API接口，业务层。项目通过华为his部署，灰度发布。
#### 技术栈选型

1. [微服务技术栈有哪些？](docs/micro-stack.md)

### 网关层
网关应用，提供网关路由转发、降级、熔断、请求处理等网关功能。
gateway-admin 提供路由应用管理，包括路由配置，设置灰度分流。
网关主要做了一件事：请求过滤。我们在网关处理一些非业务逻辑的事情，权限认证、缓存、请求路由等。
#### 常用开源网关组件
- Kong
- zuul

#### API网关


### 注册中心
- Zookeeper
- nacos
- euraka

#### nacos
使用nacos替代eureka为服务的注册中心。

1. [SpringCloud Euraka](docs/springcloud.md)


#### 治理策略

1. [治理策略](docs/micro-governance.md)


#### redis

1. [redis](docs/redis.md)


### 运维服务层

#### 系统监控

1. [Kibana](docs/kibana.md)

2. [druid](docs/druid.md)

#### 部署

部署发布使用华为鲲鹏计算云，RDS的MySQL集群，灰度发布。项目打成war包，使用tomcat集群。生产环境操作需提交变更号，经过专家评审，审批通过后部署。

1. [部署模式](docs/micro-deployment.md)
2. [tomcat集群](docs/deploy.md)

##### Docker
Docker是一个开源的容器引擎，它有助于更快地交付应用。方便快捷已经是 Docker的最大优势，过去需要用数天乃至数周的任务，在Docker容器的处理下，只需要数秒就能完成。

Docker-compose 是 docker 提供的一个命令行工具，用来定义和运行由多个容器组成的应用。使用 compose，我们可以通过 YAML 文件声明式的定义应用程序的各个服务，并由单个命令完成应用的创建和启动。

##### tomcat集群
-[tomcat集群](docs/deploy.md)

#### 缓存
- [为什么使用redis？redis使用不当会造成哪些后果](docs/cache/redis.md)

### 分布式

#### elasticsearch

- [elasticsearch简介](docs/microservice/elasticsearch.md)

#### 消息队列
1. [消息队列选型](docs/mq.md)

## 工具篇
### Linux
- [linux命令](docs/microservice/linux.md)

### Docker

- [Docker 解读](docs/microservice/Docker.md)

### Maven

- [Maven 模块](docs/orm/maven.md)

## 其他
### jvm原理
- [jvm内存模型和垃圾回收](docs/basic/JVM.md)

### 并发
- [多线程并发及juc包](docs/basic/concurrent.md)


## 说明

**文档在不断更新完善中...**

Markdown 格式参考：[Github Markdown格式](https://guides.github.com/features/mastering-markdown/)，表情素材来自：[EMOJI CHEAT SHEET](https://www.webpagefx.com/tools/emoji-cheat-sheet/)。

利用 docsify 生成文档部署在 Github pages: [docsify 官网介绍](https://docsify.js.org/#/)
### 作者的其他开源项目推荐
1. [Micro-Service-Guide](https://github.com/wangcongbirley/Micro-Service-Guide) :核心知识点汇总及实践指南。
2. [Vue-Beginner-Guide](https://github.com/wangcongbirley/Vue-Beginner-Guide) : 新手入门 Vue项目教程。
3. [Audition-Collection](https://github.com/wangcongbirley/Audition-Collection) : 工具-程序员面试题汇总。
### 关于转载

如果你需要转载本仓库的一些文章到自己的博客的话，记得注明原文地址就可以了。

### 如何对该开源文档进行贡献

1. 笔记内容大多是手敲，所以难免会有疏漏，你可以帮我找错别字。
2. 很多知识点我可能没有涉及到，所以你可以对其他知识点进行补充。
3. 现有的知识点难免存在不完善或者错误，所以你可以对已有知识点进行修改/补充。
4. 想要贡献此项目吗？加入社区吧，在Issue里申请即可。

### 联系我
>邮箱：wangcongbirley@foxmail.com
