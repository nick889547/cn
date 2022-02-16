# 事件通知
事件通知是针对资源生命周期中平台底层基础设施维护、资源重要属性变更或某些操作执行结果所发送的通知。基于事件用户可及时获知资源动态，完善云上业务的自动化运维和监控流程。<br>

## 事件列表 
云主机目前提供以下事件通知：
<table>
	<thead>
    <tr>
	<th width="100">事件类型</th>
      	<th width="190">事件名称</th>
      	<th width="200">事件代码</th>
        <th width="280">事件描述</th>
        <th>应对建议</th>
    </tr>
	</thead>
	<tbody>
    <tr>
        <td rowspan="3">异常事件</td>
        <td> 实例创建失败</td>
        <td> SystemFailure.Delete</td>
        <td> 实例创建请求成功后，由于系统原因导致的资源回滚删除。 </td>
        <td> 尝试重新创建，如仍无法成功请联系客服。</td>
    </tr>
    <tr>
        <td> 系统异常实例迁移</td>
        <td> SystemFailure.Migrate</td>
        <td> 物理机故障物理机故障导致实例不可用后进行的关机迁移。后进行的关机迁移。 </td>
        <td> 关注业务影响。</td>
    </tr>   
   <tr>
        <td> 系统异常实例不可用</td>
        <td> SystemFailure.Fault</td>
        <td> 物理机故障导致实例不可用，但实例规格不支迁移（带本地数据盘的规格，如存储优化型，GPU型）。 </td>
        <td> 联系客服，确认本地数据可以清除后由后台操作迁移。</td>
    </tr>
    <tr>
        <td rowspan="4">欠费/到期</td>
        <td> 实例停止（资源到期）</td>
        <td>InstanceExpiration.Stop</td>
        <td> 包年包月计费实例到期后停服。 </td>
        <td> 如继续使用请续费后重新启动；如不再使用请确保重要数据已备份，随后操作删除或等待系统7日后自动删除。</td>
    </tr>
    <tr>
        <td> 实例删除（资源到期）</td>
        <td> InstanceExpiration.Delete</td>
        <td> 包年包月计费实例到期7天后删除。 </td>
        <td>  </td>
    </tr>
    <tr>
        <td> 实例停止（资源欠费）</td>
        <td> AccountArrearage.Stop</td>
        <td> 按配置计费实例欠费后停服。 </td>
        <td> 如继续使用请充值后重新启动；如不再使用请确保重要数据已备份，随后操作删除或等待系统7日后自动删除。</td>
    </tr>
    <tr>
        <td> 实例删除（资源欠费）</td>
        <td> AccountArrearage.Delete</td>
        <td> 按配置计费实例欠费7天后删除。 </td>
        <td>  </td>
    </tr> 
    <tr>
        <td> 状态变更</td>
        <td> 实例状态变更</td>
        <td> StateChange </td>
        <td> 用户操作或系统行为导致的实例状态变更（目前仅支持创建和删除两类操作导致的状态变更）。 </td>
        <td> 关注状态变更是否符合预期。 </td>
    </tr>        
</table> 
 
## 事件格式
云主机事件是基于 [云事件](https://www.jdcloud.com/cn/products/cloud-events) 产品提供的服务。事件格式规范示例如下，其中，**detail**为事件详情，不同事件的信息项不尽相同，具体内容可参考下方的 [事件通知详情](event-overview#event-details)。

**以实例创建成功从pending状态变为running状态为例**
```JSON
{
	"detail":{
		"eventAction":"StateChange",
		"eventTime":"2021-03-18 11:40:38",
		"instanceCurrentState":"running",
		"instanceId":"i-eiu****bqp",
		"instanceLastState":"pending"
		},
	"detailType":"StatusNotification",
	"id":"1xo6n4os********6g2d5721f2",
	"pin":"iaasdevops",
	"region":"cn-east-1",
	"resources":[
		"i-eiuciglbqp"
	],
	"source":"jcloud.vm",
	"time":"2021-03-18T11:49:46+0800",
	"version":""	
}
```
<div id="event-details"></div>

## 事件通知详情

云事件服务提供事件订阅功能，可指定事件和资源订阅并设置事件目的地，在短信和邮件等通知途径中，事件详情会以以下形式发送。
* [实例创建失败](event-overview#user-content-1)
* [系统异常实例迁移](event-overview#user-content-2)
* [系统异常实例不可用](event-overview#user-content-3)
* [实例停止（资源到期）](event-overview#user-content-4)
* [实例删除（资源到期）](event-overview#user-content-5)
* [实例停止（资源欠费）](event-overview#user-content-6)
* [实例删除（资源欠费）](event-overview#user-content-7)
* [实例状态变更](event-overview#user-content-8)

<div id="user-content-1"></div>

### 实例创建失败
* 事件代码：SystemFailure.Delete
* 事件通知说明：此事件会在创建失败开始删除和删除成功时刻发送两条通知（由于删除会导致资源状态变更，因此同时会触发状态变更事件，详见下方StateChange），事件详情如下：
```JSON
{
	"eventAction":"SystemFailure.Delete",
	"eventState":"Executing",
	"eventTime":"2021-02-25 20:13:35",
	"instanceId":"i-ai0****net"
}
```
```JSON
{
	"eventAction":"SystemFailure.Delete",
	"eventState":"Executed",
	"eventTime":"2021-02-25 20:13:39",
	"instanceId":"i-ai0****net"
}
```

<div id="user-content-2"></div>

### 系统异常实例迁移
* 事件代码：SystemFailure.Migrate
* 事件通知说明：此事件会在开始迁移和迁移完成后发送两条通知，事件详情如下：
```JSON
{
	"eventAction": "SystemFailure.Migrate",
	"eventState":"Executing",
	"eventTime": "2021-02-25 06:44:06",
	"instanceId": "i-bc4****9oh"
}
```
```JSON
{
	"eventAction": "SystemFailure.Migrate",
	"eventState":"Executed",
	"eventTime": "2021-02-25 06:44:26",
	"instanceId": "i-bc4****9oh"
}
```

<div id="user-content-3"></div>

### 系统异常实例不可用
* 事件代码：SystemFailure.Fault
* 事件通知说明：此事件会在物理机故障，确认实例不可用后发送一条通知，事件详情如下：
```JSON
{
	"eventAction": "SystemFailure.Fault",
	"eventTime": "2021-02-25 09:51:27",
	"instanceId": "i-qj7****e7m"
}
```

<div id="user-content-4"></div>

### 实例停止（资源到期）
* 事件代码：InstanceExpiration.Stop
* 事件通知说明：此事件会在开始停止和停止完成后发送两条通知，事件详情如下：
```JSON
{
	"eventAction": "InstanceExpiration.Stop",
	"eventState": "Executing",
	"eventTime": "2021-02-25 11:00:14",
	"instanceId": "i-l16****r0v"
}
```
```JSON
{
	"eventAction": "InstanceExpiration.Stop",
	"eventState": "Executed",
	"eventTime": "2021-02-25 11:00:20",
	"instanceId": "i-l16****r0v"
}
```

<div id="user-content-5"></div>

### 实例删除（资源到期）
* 事件代码：InstanceExpiration.Delete
* 事件通知说明：此事件会在开始删和删除完成后发送两条通知，事件详情如下：
```JSON
{
	"eventAction": "InstanceExpiration.Delete",
	"eventState": "Executing",
	"eventTime": "2021-02-25 11:00:14",
	"instanceId": "i-l16****r0v"
}
```
```JSON
{
	"eventAction": "InstanceExpiration.Delete",
	"eventState": "Executed",
	"eventTime": "2021-02-25 11:00:20",
	"instanceId": "i-l16****r0v"
}
```

<div id="user-content-6"></div>

### 实例停止（资源欠费）
* 事件代码：AccountArrearage.Stop
* 事件通知说明：此事件会在开始停止和停止完成后发送两条通知，事件详情如下：
```JSON
{
	"eventAction": "AccountArrearage.Stop",
	"eventState": "Executing",
	"eventTime": "2021-02-25 11:00:14",
	"instanceId": "i-l16****r0v"
}
```
```JSON
{
	"eventAction": "AccountArrearage.Stop",
	"eventState": "Executed",
	"eventTime": "2021-02-25 11:00:20",
	"instanceId": "i-l16****r0v"
}
```

<div id="user-content-7"></div>

### 实例删除（资源欠费）
* 事件代码：AccountArrearage.Delete
* 事件通知说明：此事件会在开始删除和删除完成后发送两条通知，事件详情如下：
```JSON
{
	"eventAction": "AccountArrearage.Delete",
	"eventState": "Executing",
	"eventTime": "2021-02-25 11:00:14",
	"instanceId": "i-l16****r0v"
}
```
```JSON
{
	"eventAction": "AccountArrearage.Delete",
	"eventState": "Executed",
	"eventTime": "2021-02-25 11:00:20",
	"instanceId": "i-l16****r0v"
}
```

<div id="user-content-8"></div>

### 实例状态变更
* 事件代码：StateChange
* 事件通知说明：**目前仅支持实例创建和删除触发的状态变更事件**，此事件会在每有状态变化时发送一条通知，通知中包含之前状态和当前状态，事件详情如下：<br>

例：实例创建成功
```JSON
{
	"eventAction": "StateChange",
	"eventTime": "2021-02-25 11:00:30",
	"instanceCurrentState": "pending",
	"instanceId": "i-x0r****q2b",
	"instanceLastState": ""
}
```
```JSON
{
	"eventAction": "StateChange",
	"eventTime": "2021-02-25 11:00:52",
	"instanceCurrentState": "running",
	"instanceId": "i-x0r****q2b",
	"instanceLastState": "pending"
}
```
例：实例创建失败
```JSON
{
	"eventAction":"StateChange",
	"eventTime":"2021-02-26 19:55:18",
	"instanceCurrentState":"pending",
	"instanceId":"i-mob****hpa",
	"instanceLastState":""
}
```
```JSON
{
	"eventAction": "StateChange",
	"eventTime": "2021-02-26 19:55:39",
	"instanceCurrentState": "error",
	"instanceId": "i-mob****hpa",
	"instanceLastState": "pending"
}
```
例：实例删除成功
```JSON
{
	"eventAction": "StateChange",
	"eventTime": "2021-03-19 18:42:14",
	"instanceCurrentState": "deleting",
	"instanceId": "i-5kh****v3b",
	"instanceLastState": "stopped"
}
```
```JSON
{
	"eventAction": "StateChange",
	"eventTime": "2021-03-19 18:42:16",
	"instanceCurrentState": "terminated",
	"instanceId": "i-5kh****v3b",
	"instanceLastState": "deleting"
}
```

## 订阅事件通知
* 前往 [云事件服务](https://events-console.jdcloud.com/event/list) 控制台,点击**创建订阅规则**
* 在**基本信息**中填写自定义名称和描述
* 在**事件源**配置项中依次做如下选择：
  *  事件来源类型：**系统事件**
  *  事件来源：**云主机**
  *  事件类型：参照上方事件列表，选择事件一级分类
  *  事件筛选：选择事件类型下的全部事件或指定个别事件
  *  订阅对象：如需订阅**实例创建失败**事件，请务必选择订阅**全部对象**；其他事件可选择订阅“部分对象”指定资源id订阅
* 在**事件目的地**中，选择短信或邮件方式，并添加联系人或联系组
![](https://img1.jcloudcs.com/cn/image/vm/event.png)
   
> 订阅提示：<br>[消息管理控制台](https://message-console.jdcloud.com/message/message-settings) 提供针对全部资源由于欠费或到期导致的停服和释放的通知，如同时订阅云主机事件中的**欠费/到期**事件，会收到两类通知，请视情况选择性订阅。
    
## 相关参考

[云事件服务](https://docs.jdcloud.com/cn/cloudevents/product-overview)

 
  
 
   

