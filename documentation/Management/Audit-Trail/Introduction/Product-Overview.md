# 操作审计概述

操作审计（Audit Trail）是京东云提供的一项服务，用于记录用户账号对各类 API 调用历史记录，提供操作记录查询。用户可通过AuditTrail保存的所有操作记录，实现精确追踪、还原用户行为审计，对于安全分析，资源变更追查，合规审查有非常重要的作用。

### 工作原理
在用户创建京东云账户时，AuditTrail将会被启用 。当用户的京东云账户中发生活动时，该活动将被记录在AuditTrail事件中。用户可以轻松便捷的查看AuditTrail控制台中的事件。
通过事件历史记录，用户可以查看、搜索京东云账户中过去180天所支持的活动。您可以根据条件查询检索或者下载至本地，以进一步存档、分析和响应用户的京东云资源的变化。
