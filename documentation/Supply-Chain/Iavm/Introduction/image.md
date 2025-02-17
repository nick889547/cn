# 镜像介绍


镜像是轻量云主机运行环境的模板，包含操作系统和预装的软件以及相关配置。镜像和主机密不可分，创建轻量云主机必须指定镜像，而主机创建后，可以通过制作镜像将系统盘进行备份并记录其关联关系，后续可以基于镜像快速启动任意数量轻量云主机。



## 镜像类型

 轻量云主机支持三类镜像： 应用镜像、系统镜像和自定义镜像，可根据实际需要，选择适合的镜像创建轻量云主机。

 | 镜像类型 | 说明 | 
| :-----:| :----: | 
| 应用镜像 | 应用镜像包含操作系统、应用软件以及应用运行所需的环境，选用应用镜像创建轻量云主机，应用会自动部署安装，<br>您可以直接访问和使用应用。 | 
| 系统镜像 | 系统镜像是由京东云提供和维护的公共镜像，包括多个CentOS、Ubuntu及Windows Server发行版本<br>（Windows镜像目前免费提供正版License），安装系统镜像的轻量云主机，是纯净的操作系统环境，<br>可根据实际需求安装应用和配置环境。 | 
| 自定义镜像 | 自定义镜像是基于轻量云主机创建的镜像，您可以制作自定义镜像备份轻量云主机的运行环境和数据，<br>实现业务的恢复或批量的快速部署。 | 

## 应用镜像


| 镜像名称 | 镜像说明 | 
| :-----:| :----: | 
| WordPress | WordPress是使用最广泛的博客和内容管理系统，支持丰富的插件和模板，功能强大，易于扩充功能。您可以使用它快速搭建独立的博客、论坛等网站，也可以做CMS使用。该镜像基于CentOS 7.6 操作系统 | 
| 宝塔Linux面板 | 宝塔Linux面板（BT-Panel）是一款操作简便、功能强大的服务器运维管理面板，通过web界面，就可以轻松安装和管理服务器软件，查看服务器使用情况，对文件进行可视化管理，能够极大提升运维管理效率。该镜像基于CentOS 7.9 位操作系统 | 
| Ghost博客系统 |Ghost 是一款设计简约、主题精致的个人博客系统，Ghost支持多用户创建和编辑，支持Markdown格式撰写文章，编辑的内容可即时预览。该镜像是镜像基于CentOS 7.6 操作系统 | 
| 零代码开发平台 | 明道云零代码开发平台可以进行低代码或无代码搭建个性化的CRM、ERP、OA、项目管理、进销存等企业信息化系统，还可以管理生产、销售、采购、人事等所有企业活动 | 
| ASP.NET	 | ASP.NET是使用.NET 构建的轻量级Web应用框架，可以构建应用、网页和网站服务。该镜像是镜像基于WindowsServer2019操作系统 | 
| 协同办公-工具箱 | 协同办公-工具箱包含Zentao禅道项目管理、ONLYOFFICE Document Server 文档编辑/预览服务器、网盘系统【Nextcloud 在线文件管理/云存储系统】、MediaWiki百科软件搭建知识库、Superset数据可视化5个工具。该镜像是基于CentOS7.6 操作系统 | 
| LAMP-PHP	 | LAMP 是最常见的Web应用框架，预装了Apache、MySQL和PHP及相关组件支持，兼容大部分PHP应用程序。 | 
| PrestaShop电商平台		 | PrestaShop 是操作简单，使用方便的电子商务平台，支持 600多个功能，5,000多个模块和主题的选购或内置，PrestaShop官方构建了一个非常完善、健康的商业化服务生态，是您搭建电子商务网站的优选。该镜像是基于CentOS 7.6 操作系统	 | 

## 系统镜像

| 镜像名称 | 镜像版本 | 
| :-----:| :----: | 
| CentOS | CentOS 是一个基于Red Hat Linux 发行的稳定版本 |
| Ubuntu | Ubuntu是一个以桌面应用为主的Linux操作系统 |
| Windows Server | Windows Server是基于的Windows 的服务器操作系统 |



