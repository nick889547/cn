# deleteSubnet


## 描述
删除子网

## 请求方式
DELETE

## 请求地址
https://vpc.jdcloud-api.com/v1/regions/{regionId}/subnets/{subnetId}

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |Region ID|
|**subnetId**|String|True| |Subnet ID|

## 请求参数
无


## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String|请求ID|


## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
|**400**|Invalid parameter|
|**401**|Authentication failed|
|**404**|Not found|
|**409**|Parameter conflict|
|**500**|Internal server error|
|**503**|Service unavailable|

## 请求示例

调用方法、签名算法及公共请求参数请参考[京东云OpenAPI公共说明](https://docs.jdcloud.com/common-declaration/api/introduction)。
- 请求示例：删除资源ID为subnet-5g97rio80i的子网

DELETE
```
  /v1/regions/cn-north-1/subnet/subnet-5g97rio80i

```

## 返回示例
```
{
"requestId":"35e06de5-6a1b-41f1-9e3a-53f86d84dji4"
}
```
