## 弹性公网IP

### 产品概述

弹性公网IP是专用于动态云计算的静态IP。与传统静态IP不同，弹性IP可以与任一分布式云物理服务器绑定，您可以绑定至A也可以绑定至B。 当分布式云物理服务器发生故障或可用区存在故障时，您可以将IP地址重新映射到健康的分布式云物理服务器上，这样您便可以在处理服务器问题的同时提供服务，弹性公网IP又称“边缘云公网IP”。（注意：此服务器特指“分布式云物理服务器”）

### 使用限制

您在使用弹性公网IP时请注意以下使用限制。

1、目前每个京东云账户支持每个节点最多申请10个弹性公网IP，如需更多配额通过[提交工单](https://ticket.jdcloud.com/applyorder/submit)提升配额。<br/>

2、弹性公网IP仅可与同节点同运营商资源（包括分布式云物理服务器）进行绑定。<br/>

3、弹性公网IP支持与分布式云物理服务器绑定、解绑操作。<br/>

4、单个弹性公网IP可以在一天之内进行多次绑定/解绑操作。如果需要为已绑定弹性公网IP的资源更换IP，必须先将资源与当前的IP解绑，之后再进行新IP的绑定。<br/>

5、目前包年包月的资源不允许删除。<br/>

### 计费概述

弹性公网IP支持包年包月和按配置两种计费方式，弹性公网IP支持带宽和额外上行带宽2个计费项。包年包月：按照带宽配置预付费。按配置：按照带宽配置每小时出账单。

**包年包月计费**

包年包月为预付费方式，一次性支付一个月、多个月或多年的费用，适用于提前预估弹性公网IP带宽需求的场景，价格相比按配置计费更低廉。

详细说明：
提前支付数月或数年的费用，目前购买时间段支持1个月~9个月、1年、2年、3年；费用在您创建资源时一次性扣除；示例：您在2017-8-2 10:00:00购买1个月1M带宽、1M额外上行带宽的电信弹性公网IP，月单价总和为23元，则您需要支付的费用为23=23* 1元，您可以使用该资源至2017-9-2 23:59:59。

包年包月的资源在到期前不支持执行删除操作，为了保障您的使用权益，请确认业务需求后进行购买。

包年包月计费订单的到期时间为订单开始时间当日起向后第N个自然月或自然年的23:59:59； 例如：订单的开始时间为2016年1月1日 15:00:00，购买时长为1个月，则到期时间为2016年月2日1日 23:59:59。

##### 到期停服说明

当您的包年包月付费网络资源到期时间早于或等于当前时间，则您的付费网络资源状态会变为已到期。到期后付费网络资源将被停止服务，不能继续使用；

您的包年包月付费网络资源到期前，京东智联云会向您发送邮件、短信，提醒您的资源即将到期，请您注意查看并及时续费；

您的付费网络资源到期后立即停服，会向您发送邮件和短信通知您的资源到期停服，请您务必注意查看通知并及时充值，以免造成不必要的损失；

从停止服务时刻起，您的付费网络资源保留7天，7天后系统回收资源，无法找回；控制台界面将只能执行续费操作；

您续费后被停用资源可正常使用。

**按配置计费**

开通要求：为保证您的正常使用，开通按配置计费的资源时您的账户余额及可用代金券之和不低于消费门槛50元。

##### 欠费停服说明

当您的账户中余额及可用代金券的总和不足以支付下一计费周期费用时，导致扣款不成功，您的付费网络资源（弹性公网IP）的状态会变为欠费；

当您的付费网络资源欠费后，可继续正常使用3小时，3小时后将欠费停止服务且停止扣费；控制台界面将只能执行删除操作；

当您的付费网络资源欠费后，会向您发送邮件和短信，通知您的资源已欠费，请您务必注意查看通知并及时充值，以免造成不必要的损失；

从停止服务时刻起，您的付费网络资源保留7天，7天后系统回收资源，无法找回；

当您补缴欠费金额后，被停用的付费网络资源方可正常使用；

如您不想继续使用按配置的付费网络资源，请及时将该资源进行删除。

### 价格总览

详见弹性公网IP[价格总览](../../Pricing/Price-Overview.md)。

### 创建弹性公网IP

- 打开控制台，在左侧导航栏点击弹性公网IP，进入弹性公网IP列表页，点击 **申请** 按钮，弹出创建配置窗口；<br/>

- 根据需求选择节点，运营商，带宽计费模式（支持按包年包月、按配置、加入共享带宽3种计费方式），线路类型，IP类型(IPv4和IPv6)，带宽上限，额外带宽上限，购买时长和数量，点击 **确定** 按钮，即可创建1个弹性公网IP。<br/>

- 包年包月资源开通自动续费功能。勾选自动续费待资源创建后，自动续费属性和时长均修改。按月购买，则自动续费周期为1个月；按年购买，则自动续费周期为1年，按年自动续费享受自动续费折扣。<br/>

### 查看弹性公网IP

- 打开控制台，在左侧导航栏点击弹性公网IP，进入弹性公网IP列表页，查看弹性公网IP信息；<br/>

- 或点击弹性公网IP **IP地址** ，跳转详情页，查看弹性公网IP详情信息。<br/>


### 绑定资源

- 打开控制台，在左侧导航栏点击弹性公网IP，进入弹性公网IP列表页，选择目标EIP，点击操作中的 **绑定资源** 按钮，或进入详情页后点击操作中的 **绑定资源** 按钮，弹出信息如下；<br/>

- 按照需求选择资源类型，网络接口数量，目标网络接口名称，点击 **确定** 按钮，即可完成绑定。

- 限制条件：EIP IPv4支持绑定已开通内网IPv4或别名IPv4的分布式云物理服务器资源；EIP IPv6支持绑定已开通内网IPv4或别名IPv6的分布式云物理服务器资源；<br/>

### 解绑资源

- 打开控制台，在左侧导航栏点击弹性公网IP，进入弹性公网IP列表页，选择目标EIP，点击操作中的 **解绑资源** 按钮，或进入详情页后点击操作中的 **解绑资源** 按钮，即可完成解绑。<br/>

### 修改带宽

- 打开控制台，在左侧导航栏点击弹性公网IP，进入弹性公网IP列表页，选择目标EIP，点击操作中的 **修改带宽** 按钮，或进入详情页后点击操作中的 **修改带宽** 按钮，弹框信息如下：<br/>

- 选择需要调整的带宽，额外上行带宽大小，即可完成操作。<br/>

### 加入共享带宽

- 打开控制台，在左侧导航栏点击弹性公网IP，进入弹性公网IP列表页，选择目标EIP，点击操作中的 **加入共享带宽** 按钮，或进入详情页后点击操作中的 **加入共享带宽** 按钮，弹框选择需要加入的共享带宽，即可完成操作。<br/>

- 弹性公网IP 加入共享带宽后，注意：<br/>
  1、原本的带宽/额外上行带宽值失效，变为和共享带宽的相同；<br/>
  2、原来的计费模式失效，变为单纯的IP，不额外计带宽费用；<br/>
  3、预付费包年包月的弹性公网IP暂时不支持添加到共享带宽，仅支持配置的弹性公网IP加入共享带宽。<br/>
  
- 限制条件：不支持EIP IPv6加入共享带宽IPv6。<br/>

### 移出共享带宽

- 打开控制台，在左侧导航栏点击弹性公网IP，进入弹性公网IP列表页，选择目标EIP，点击操作中的 **移出共享带宽** 按钮，或进入详情页后点击操作中的 **移出共享带宽** 按钮，即可完成操作。<br/>

- 弹性公网IP移出共享带宽后，注意：<br/>
  1、恢复加入共享带宽之前的带宽、额外上行带宽上限；<br/>
  2、恢复加入共享带宽前的计费模式。<br/>

### 续费

- 打开控制台，在左侧导航栏点击弹性公网IP，进入弹性公网IP列表页，选择目标EIP，点击操作中的 **续费** 按钮，或进入详情页后点击操作中的 **续费** 按钮，弹框选择需要续费的时长，点击 **确认** 按钮，跳转到 **支付确认页面**，点击 **立即支付**，即可完成操作。<br/>

- 注意：按配置计费的弹性公网IP进行续费操作后会转为包年包月资源。

### 删除

- 打开控制台，在左侧导航栏点击弹性公网IP，进入弹性公网IP列表页，选择目标EIP，点击操作中的 **删除** 按钮，或进入详情页后点击操作中的 **删除** 按钮，点击 **确认** 按钮，即可完成操作。<br/>

- 注意：包年包月计费的弹性公网IP不支持删除操作。
