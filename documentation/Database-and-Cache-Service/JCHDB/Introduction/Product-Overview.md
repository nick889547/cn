# 产品概述

**京东云数据库** **ClickHouse**是京东云基于开源 ClickHouse 打造的联机分析（OLAP）服务，拥有无与伦比的查询性能，其写入和查询速度可达到传统数据仓库的数倍，为用户提供实时数据分析能力。具有开箱即用、超高性能、便捷运维等特点。广泛应用于**流量分析、精准营销、用户画像、广告实时竞价、BI报表分析、日志分析、促销选品、物联网**等业务场景。


#### 产品特性
- 真正的面向列的DBMS

- 数据高效压缩

- 多核并行处理

- 在多个服务器上分布式处理

- 支持在线查询

- 支持近似预估计算

- 数据复制和对数据完整性的支持

- 全面支持IPV6

  

## 功能简介
### 分布式架构，多数据副本
- 多数据副本：可自定义的数据副本数，数据副本可读可写，充分满足大型业务系统的复杂需求。

- 副本自动复制：使用异步多主复制。写入任何可用的副本后，数据将分发到所有剩余的副本。系统在不同的副本上保持相同的数据。

- 故障自动修复：当检测到数据故障时，系统会自动从其他正常的数据副本中同步数据，进行修复。



### 规格灵活定义
- 提供不同规格的节点，满足不同场景需求

- 采用云盘高可靠存储，可灵活调整存储空间

- 支持上百个shard节点

  

### 弹性伸缩
- 支持节点规格升/降配
- 支持存储空间扩容
- 用户可根据业务需求灵活调整配置，弹性灵活


 
### 便捷运维
- 多维度监控：提供数据库实例级和各节点级别的可视化监控平台，帮助业务及时感知集群运行状态。

- 自定义告警规则：可根据监控指标自定义告警规则，并通过短信，Email等方式进行通知。

  

### 多种安全防护机制
- 系统安全：宿主机位于防火墙保护之下，只开放必需的端口，且安装有各种系统补丁，修补安全漏洞，能够抵御各种恶意攻击，保障数据库安全。

- 私有网络隔离：实例默认运行在逻辑隔离的私有网络（VPC）中，避免了数据库直接暴露在公网上，可规避绝大部分攻击。

- 自定义安全策略：通过IP白名单可定义和强化安全策略，进一步加强数据库的安全性。

  

## 参考资料
- ClickHouse 官网：    https://clickhouse.tech/
- ClickHouse 官方文档：https://clickhouse.tech/docs/zh/

