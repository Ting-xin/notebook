# Docker

[gitbook](https://yeasy.gitbook.io/docker_practice/)

[toc]

## 前言

Docker是个划时代的开源项目，它彻底释放了计算虚拟化的威力，极大的提高了应用的维护效率，降低了云计算应用开发的成本，使用Docker，可以让应用的部署、测试和分发都变得前所未有的高效和轻松

## Docker 简介

![img](../image/docker-on-linux.png)

Docker 在容器的基础上，进行了进一步的封装，从文件系统、网络互联到进程隔离等等，极大的简化了容器的创建和维护，使得Docker技术比虚拟机技术更为轻便、快捷

![img](../image/virtualization.png)

![img](../image/docker.png)

- 更高效的利用系统资源
- 快速的启动时间
- 一直的运行环境
- 持续交付和部署
- 更轻松的迁移
- 更轻松的维护和扩展

## 基本概念

Docker 包括三个基本概念：镜像（Image）、容器（Container）、仓库（Repository）

### 镜像

们都知道，操作系统分为 **内核** 和 **用户空间**。对于 `Linux` 而言，内核启动后，会挂载 `root` 文件系统为其提供用户空间支持。而 **Docker 镜像**（`Image`），就相当于是一个 `root` 文件系统。

**Docker 镜像** 是一个特殊的文件系统，除了提供容器运行时所需的程序、库、资源、配置等文件外，还包含了一些为运行时准备的一些配置参数（如匿名卷、环境变量、用户等）。镜像 **不包含** 任何动态数据，其内容在构建之后也不会被改变。

### 容器

镜像（Image）和容器（Container）的关系就像是面向对象程序设计中的类和实例一眼，镜像是静态的定义，容器是镜像运行时的实体，容器可以被创建、启动、停止、删除、暂停等

容器的实质是进程，但与直接在宿主执行的进行不同，容器进程运行于属于自己的独立的命名空间，因此容器可以拥有自己的root文件系统，自己的网络配置、自己的进程空间，容器的进程是运行在一个隔离的环境里。容器不应该向其存储层中写入任何数据、容器存储层要保持无状态化。所有的文件写入操作，都应该使用数据卷（Volume）或者绑定宿主目录

### 仓库

镜像构建完成后，可以很容易在当前宿主机上运行，但是，如果需要在其它服务器上使用这个镜像，我们就需要一个几种的存储、分发镜像的服务，Docker Registry 就是这样的服务

一个 Docker Registry 中可以包含多个仓库（Repository），每个仓库可以包含多个标签，每个标签对应一个镜像

## 安装Docker

Docker分为 stable test 和 nightly 三个更新频道
