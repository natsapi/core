**简要描述：**

- 客户端接入网关-下单入口

**接入商户数据：**


**请求地址：**
- 测试:http://g.daliuliang.com.cn/placeOrder/orderGateway/placeOrder
- 生产:http://g.daliuliang.com.cn/placeOrder/orderGateway/placeOrder

**请求方式：**
- POST

**参数：**


|参数名|是否必须|类型|说明|默认值|取值范围|
|--------|:----|:--------|:---------|:------|:------|
|merchantNo |true  |string |商户号   | | 平台分配|
|userId |true  |string | 交易方用户id   | | 6-24位|
|amount |true  |String | 限价单表示下单数量，市价买单时表示买多少钱，市价卖单时表示卖多少币   | |最多小数点后面8位 |
|price |false  |String |下单价格，市价单不传该参数   | |最多小数点后面8位 |
|symbol |true  |string | 交易对名称   | | ETH/USDT|
|type |true  |string | buyMarket：市价买, sellMarket：市价卖, buyLimit：限价买, sellLimit：限价卖    | | |
|partnerOrderNo |true  |string | 接入方订单号   | |8-24位 |
|createTime |true  |string | 请求时间   | |yyyyMMddHHmmss(14位) |
|callBackUrl |true  |string | 通知地址   |必须以"http://"  或 "https://" 开头| https://www.baidu.com|
|ext1 |false  |string | 扩展参数   | | 通知时原样返回|
|sign |true  |string | 签名串   | |详情请看加解密说明 | |

 **请求示例**
```
{"data": {
		"head": {
					"merchantNo":"client",
					"sign":"29C9C89EE2AD0BF4078730F1BE7E1F38"
				},
		"body": {
					"userId":"1",
					"amount":"1",
					"price":"1",
					"symbol":"ETH/USDT",
					"type":"buyLimit",
					"partnerOrderNo":"a123456",
					"createTime":"20180711110706",
		 		}
		}
}

```

 **返回参数说明** 

|参数名|是否必须|类型|说明|取值范围|
|--------|:----|:--------|:---------|:------|
|code  |true| string  | 1-成功 2-失败| 1,2|
|msg |true   |string |返回消息| |
|data |true   |string |返回参数| |

 **返回示例**
```
{
	"code": "1",
	"msg":"ok",
	"data": "",
}
```
