# 核心概念

云上的物理计算资源，即一台运行在数据中心的云物理服务器，也即 **实例** 。

描述云物理服务器所在的数据中心，即 **地域和可用区** 。

云物理服务器适用的场景，由不同的CPU、内存、存储和网络等组成，即 **实例类型** 。

实例对内和对外的服务地址，即 **内网 IP 地址和公网IP地址** 。

基于 Web 的操作界面，即 **京东云控制台** 。

## 概念详述

### 实例
云上的物理计算资源，即一台运行在数据中心的云物理服务器，即实例。实例就是用户购买的一台京东云云物理服务器。京东云提供具有不同存储空间，计算能力，存储冗余的实例，以满足用户在不同业务场景下对实例的不同要求。当用户购买了一个实例时，可以获得其完整的控制权利，包括开机、关机、重启、带外监控等。

### 地域和可用区
我们用地域（Region）和可用区（Availability Zone）用来描述云物理服务器所在的数据中心的位置,您可在特定的地域、可用区购买云物理服务器。

地域（Region）指独立的地理区域。一个地域内都有多个相互隔离的数据中心，称为可用区（Availability Zone）。

不同地域是完全独立的，这可实现最大程度的容错能力和稳定性。每个可用区也是独立的，但同一地域下的可用区可以通过低时延的内网链路相连。您可购买不同位置的云物理服务器，并且建议您将业务部署在不同可用区以避免单点故障导致的服务不可用状态。

以下是云物理服务器已开放售卖或正在建设的数据中心所在地域及可用区。

<table>
    <tr>
        <td >&nbsp;</td> 
        <td ><B>地域</B></td> 
		<td ><B>可用区</B></td>
		<td ><B>开放状态</B></td>		
    </tr>
    <tr>   
        <td rowspan="4"><B>中国大陆境内</B></td>
		<td >华北-北京</td>
		<td >可用区A、可用区B、可用区C</td>
		<td >已开放</td>
    </tr>
    <tr>   
        <td >华东-上海</td>
		<td >可用区A、可用区B</td>
		<td >筹备中</td>
    </tr>
	<tr>   
        <td >华东-宿迁</td>
		<td >可用区A</td>
		<td >筹备中</td>
    </tr>
	<tr>   
        <td >华南-广州</td>
		<td >可用区A</td>
		<td >筹备中</td>
    </tr>
</table>


### 内网IP
在基础网络模式之下，用户指定子网下的内网IP地址由系统统一分配。如果您在操作系统内部自行变更内网IP，会导致内网通讯中断。同一数据中心内云物理服务器之间通过内网IP进行的通讯流量是免费的。内网IP用于云物理服务器之间内网互访。

### 公网IP
公网IP地址是用户访问云物理服务器以及云物理服务器实例对外提供服务的主要方式。一台云物理服务器只能绑定一个公网IP。您可以动态调整公网IP的带宽峰值。<br/>
在基础网络模式下，用户创建云物理服务器可以选择暂不购买公网IP，但是后续不可添加公网IP。<br/>
在私有网络模式下，用户创建云物理服务器可以选择暂不购买公网IP，后续可添加弹性公网IP，即选择需要添加的云物理服器，将EIP绑定即可。<br/>

