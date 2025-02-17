
#### AMC 目前支持哪些公有云平台？
- 迁移源平台目前支持以下公有云：
  - 阿里云
  - 华为云
  - 京东云
- 迁移目标平台目前支持：
  - 京东云

#### AMC 目前支持哪些资源自动发现及导入
目前可支持以下常用资源的自动发现及导入：
- 服务器：云服务器
- 数据库：MySQL，PostgreSQL，MongoDB，Redis
- 对象存储：存储桶（Bucket）

#### AMC 支持哪些资源的迁移
目可以提供以下常用资源的迁移工具或迁移方案：
- 云主机迁移，提供以下两种迁移方式：
  - 私有镜像导入
  - 主机在线迁移
- 数据库迁移：提供数据迁移、数据订阅和数据同步服务，可满足数据上云、业务异步解耦、数据异地灾备、业务系统数据流转等业务场景。支持以下数据库：
  - MySQL
  - MariaDB
  - Percona
  - PostgreSQL
  - SQL Server
  - MongoDB
  - Redis
- Elasticsearch：可以通过 OSS 快照方式、Reindex 方式和 Logstash 方式，实现京东云 ES 间的数据迁移、自建/第三方 ES 迁移至京东云等场景。
- OSS：提供在线迁移和离线迁移两种方式。

#### OSS 迁移支持单个文件的最大大小是多少？
支持的最大单文件大小为 19.5 TB。

#### 文档上传支持单个文件的最大大小是多少？
支持的最大单文件大小为 50 MB 。

#### 文档上传支持哪些文件格式？
支持 .pdf, .docx, .doc, .xlsx, .xls, .pptx, .ppt, .png, .svg, .vsdx, .vsd, .xmind
