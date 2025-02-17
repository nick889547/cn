# 设置报警规则
可以设置监控项，创建报警规则，当检测到 Starwift 实例异常触发监控项的报警规则时，会通知报警联系组中的所有联系人。

> **说明**
> 
> 更详细的告警设置文档可以参考 云监控的帮助文档 [添加报警规则](https://docs.jdcloud.com/cn/monitoring/add-rule-in-batches)

## 操作步骤
#### 1. 进入告警设置页面
在控制台中，点击实例名，进入实例页面，选择 **监控** 页面，点击右侧 **设置报警规则**，进入到云监控的实例监控详情页。

#### 2. 设置告警规则
按照以下步骤配置信息
1）基本信息：设置规则名称，确认资源类型和已选中的实例信息。
2）触发条件：支持自定义添加，也支持绑定已有的模板信息。
  - 自定义添加：选择监控项、统计周期、统计方法、计算方式、阈值、持续周期，同时可根据需求配置报警级别。 若需配置多个触发条件，点击“添加触发条件”按钮即可配置。
     ![报警级别](../../../../../image/Cloud-Monitor/img/4-zdytj.png)    
     ![报警级别](../../../../../image/Cloud-Monitor/img/4-zdytj-0.png) 
 - 使用模板：切换至“使用模板”选项，点击下拉框，选择需要使用的模板，若需详细了解模板的详情信息，可点击“查看模板”字样，打开模板详情。  
     ![触发条件-使用模板](../../../../../image/Cloud-Monitor/img/5-symb.png)  
     ![查看模板详情](../../../../../image/Cloud-Monitor/img/9-mb-xq.png)

#### 3. 设置通知策略
通知策略的参数说明如下：  
- 通知周期：表示如果资源一直处于告警状态，未恢复正常，间隔多久发送下一次通知。提供5分钟、10分钟、15分钟、30分钟、1小时、3小时、6小时、12小时和24小时几种选项。
- 有效时段：报警短信和邮件信息仅在指定时间范围内发送，默认是全天都发送。
- 通知条件：提供“报警”和“恢复正常”两种场景，默认仅报警状态发送，必须要指定通知条件。
- 接收渠道：提供“短信”和“邮件”两种选型，默认都发送，可根据需要选择。  
- 通知对象：支持选择联系人或联系组。添加联系人和联系组击选择框底部的“账户管理-联系人管理”进入用户中心进行配置。  
- 报警回调：当资源发生告警时，京东云主动按照您配置的URL地址和POST参数进行回调。    
     ![通知策略](../../../../../image/Cloud-Monitor/img/6-tzcl.png)  
     ![报警回调](../../../../../image/Cloud-Monitor/img/6-tzcl-hd.png)
     
#### 4. 完成创建
点击页面底部的“完成创建”，则支持添加报警规则，点击“取消”按钮， 放弃本次操作。

