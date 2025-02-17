# 购买流程 
可以通过控制台购买堡垒机


## 1. 操作入口
- 进入 [堡垒机 列表页](https://bastion-console.jdcloud.com/list)，可以看到当前区域下的堡垒机 实例的概要信息，包括规格和到期时间等。
- 点击【创建】按钮，新建一个实例。

![](/image/Bastion/Instance-List.png) 
   
## 2. 购买堡垒机
在堡垒机购买页面，根据您的业务需求完成实例规格配置。

![](/image/Bastion/Instance-List1.png) 

**实例配置**

- 目前仅支持“包年包月”计费方式，关于计费方式的选择，请参考[计费规则](./Billing-Rules.md)。

**参数说明如下**

- 地域：选择堡垒机所在的地域，**堡垒机选定地域后无法更改，请慎重选择。建议堡垒机与需要管理的云主机实例处于同一地域。**
- 规格：堡垒机实例的规格，包括可管理的资产数量和支持的会话并发数量。选择规格后，您可以在规格区域下方看到具体的配额信息。更多关于配额的信息，请参见[价格总览](./Price-Overview.md)。
- 私有网络：只支持在私有网络中创建。如果用户没有私有网络及子网，可以通过【新建私有网络】和【新建子网】的链接创建私有网络和子网。创建完成后，点击【刷新】，就可以看到新创建的私有网络和子网了。
- 购买数量：要开通的堡垒机实例的数量
- 购买时长：要开通的堡垒机实例的有效期。购买的时长越长，折扣力度越大，具体以控制台为准。

## 3. 确认购买
信息输入完成后，可查看点击页面右边的价格信息，并点击【立即购买】

![](/image/Bastion/Create-Instance-1.png) 

## 4. 支付订单
然后进入订单确认页面，确认购买信息无误后，点击【立即支付】

![](/image/Bastion/Create-Instance-2.png) 

## 5. 初始化堡垒机
支付成功后自动返回实例列表页面，能看到实例状态为"初始化中"。初始化过程耗时1-2分钟，若列表中未出现新购买的堡垒机，请手工刷新列表。

![](/image/Bastion/Create-Instance-3.png) 

## 6. 创建完成
点击刷新按钮，显示实例创建完成，状态显示为“运行中”即表示正常运行

![](/image/Bastion/Create-Instance-4.png) 

