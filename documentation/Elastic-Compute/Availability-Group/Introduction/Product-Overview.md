# 概述

高可用组(Availability Group，简称AG)是京东云提供的业务高可用部署解决方案，是计算资源逻辑集合。提供了多种均衡部署的机制（置放策略），使实例分散部署在相互隔离的物理资源上，当出现硬件故障或定时维护时只会影响部分实例，最大程度规避了局部故障对高可用应用整体的影响，您的业务仍为可用状态。

**免费使用**，仅按组内资源收取相关费用。后续将支持容器类型高可用组。

## 相关概念

了解京东云高可用组时，通常会涉及到概念请参见[核心概念](Core-Concepts.md)。

<div id="user-content-1"></div>

## 置放策略

置放策略是指实例在底层硬件上分布放置的策略，高可用组支持以下三种策略：

* 物理机：高可用组内实例将严格分散在不同物理机上，单可用区实例数量上限为10；
* 交换机：高可用组内实例将严格分散在不同交换机下，单可用区实例数量上限为5；
* 故障域：高可用组内实例分散部署在相互隔离的物理资源组上，不限制组内实例数量，相同分组的实例不保障严格分散部署。

请注意：使用置放策略后，会严格遵守您指定的策略，若您的高可用组是物理机或交换机策略的，如底层硬件不足够使实例分散，部分实例将创建或加入失败。

## 主要操作

* 新建高可用组
* 灵活管理高可用组内资源，按需新增、移除云主机
* 开启/关闭自动伸缩
* 灵活配置自动伸缩策略，新增/删除自动伸缩策略
* 自定义自动伸缩通知联系人组
* 查询自动伸缩记录

