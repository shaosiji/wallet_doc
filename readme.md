
# 区块链名称对应关系

	BSC-HD 币安BSC链

	ETH-HD 以太坊主链

## 接口错误代码

* 响应正确为
```
{
  "code": 10000,
  "msg": "ok"
}
```
* 响应错误为
```
{
  "code": xxxx,
  "msg": "错误信息"
}
```
xxxx 代表响应错误码

-------------------------------------------------------------------------------------------

### 查看交易历史
```
GET /api/v1/transactions
```
**参数:**

名称 | 类型 | 是否必须 | 描述
------------ | ------------ | ------------ | ------------
address | STRING | YES |钱包地址|
type | INT | YES | 交易类型 0 为全部，1为转入 ，2为转出|
contract_address| STRING |NO | token地址，如果传空表示区块链的token地址|
page |INT | YES | page  页号从1开始 |
count |INT | YES | 每页数量 |
wallet_name |STRING | YES | 区块链名称 |	 
	
**响应:**
```	
	{
		"code": 10000,
		"msg": "success",
		"data": {
			"pageNum": 1, 				//页号
			"pageSize": 20, 			//每页数量
			"totalPage": "1", 			//最大页数
			"results": [{
				"decimal": 18,
				"fee": "0.000063",		//交易费用
				"symbol": "BNB", 		//交易token名称
				"sl_symbol": "BNB", 		//交易token符号
				"timestamp": 1693276752, 	//时间戳
				"block_number": 31264049, 	//区块号
				"gas": "21000",		 	//gas上限
				"gas_price": "3006000000", 	//gas价格
				"used_gas": "21000",		//实际使用的gas
				"value": "5000000000000000",	//交易金额
				"hash": "0x39a68058fc4ba5e372194469b347ad5c0e0efcbaecafe3401be2284897a3fe0b",	//交易hash
				"nonce": "0x2",			//随机数
				"block_hash": "0xd86ade0086c4af632984467408738606c4a6d60e5f240ddf50eeb511e846c6a3", //区块hash
				"from": "0x277d9d29c6ec9f89adeec153d96e273dab753eb6",		//转出地址
				"to": "0x96ecced577d48850017d883e1cb543418da85702",		//转入地址
				"addr_token": "",
				"status": 1						//交易状态
			}
			]
		}
	}
```
------------------------------------------------------------------------------------------
### 获取所有token 地址

```
GET /api/v1/tokens
```
**参数:**
名称 | 类型 | 是否必须 | 描述
------------ | ------------ | ------------ | ------------
page |INT | YES | page  页号从1开始 |
count |INT | YES | 每页数量 |
wallet_name |STRING | YES | 区块链名称 |	

**响应:**
```
{
	"code": 10000,
	"msg": "success",
	"data": {
		"pageNum": 1,
		"pageSize": 100,
		"totalPage": "1",
		"results": [{
			"hid": 899734962,
			"blockchain_id": 1,	//区块链id
			"blockchain": null,
			"name": "HarryPotterObamaPacMan8Inu",
			"symbol": "XRP",	//token名称
			"bl_symbol": "XRP",	//token符号
			"gas": 60000,		//gas
			"decimal": 8,
			"precision": 8,
			"balance": "",
			"price_usd": 0.2489487047716612,
			"percent_change_24h": 0,
			"asset": 0,
			"added": 0,
			"address": "0x07e0edf8ce600fb51d44f51e3348d77d67f298ae",
			"owner_address": "",
			"website": "",
			"description": "HarryPotterObamaPacMan8Inu",
			"update_contract": 0,
			"total_supply": "100000000",
			"holder_count": 0,
			"published": 0,
			"ti_link": "",
			"token_status": 0,
			"validated": 0,
			"icon_url": "https://hk.tpstatic.net/token/tokenpocket-1692428812431.png",
			"auto_add": 0,
			"dapp_code": "",
			"token_protocol": 0,
			"metadata_type": 0,
			"create_time": "2023-08-07T04:49:51+08:00",
			"Weight": 1
		}]
	}
}

```
-------------------------------------------------------------------------------------------

### 查看轮播图

```
GET /api/v1/banners
```


参数
	
名称 | 类型 | 是否必须 | 描述
------------ | ------------ | ------------ | ------------
page |INT | YES | page  页号从1开始 |
count |INT | YES | 每页数量 |	

**响应:**
	
	{
	"code": 10000,
	"msg": "success",
	"data": {
		"pageNum": 1,		//页号
		"pageSize": 20,		//每页数量
		"totalPage": "1",	//最大页数
		"results": [{
			"title": "新app上架了",	//标题
			"image_url": "http://image.com",	//图片地址
			"jump_url": "http://jump.com",		//跳转url
			"type": 0,
			"txt": "测试内容"					//内容
		}]
	}
}

-------------------------------------------------------------------------------------------

查看公告
GET /api/v1/banners

参数
	
名称 | 类型 | 是否必须 | 描述
------------ | ------------ | ------------ | ------------
page |INT | YES | page  页号从1开始 |
count |INT | YES | 每页数量 |

**响应:**
	
	{
	"code": 10000,
	"msg": "success",
	"data": {
		"pageNum": 1,		//页号
		"pageSize": 20,		//每页数量
		"totalPage": "1",	//最大页数
		"results": [{
			"title": "2023-08-30 update version",		//标题
			"type": 0,
			"txt": "see more at http://",				//内容
			"image_url": "http://"						//图片地址
		}]
	}
}

-------------------------------------------------------------------------------------------

查看rpc节点
GET /api/v1/rpcnodes

参数
	
名称 | 类型 | 是否必须 | 描述
------------ | ------------ | ------------ | ------------
page |INT | YES | page  页号从1开始 |
count |INT | YES | 每页数量 |
wallet_name |STRING | YES | 区块链名称 |	

**响应:**
	
	{
	"code": 10000,
	"msg": "success",
	"data": {
		"pageNum": 1,		//页号
		"pageSize": 20,		//每页数量
		"totalPage": "1",	//最大页数
		"results": [{
			"walletname": "ETH-HD",			//区块链名称
			"chain_name": "以太坊节点1",	//节点名称
			"rpc_url": "https://rpc.ankr.com/eth",	//rpc节点
			"icon": "",								//图标
			"remark": " "
		}]
	}
}


-------------------------------------------------------------------------------

市场行业 币安公开的接口 无需认证 

币安文档接口地址 

https://github.com/binance/binance-spot-api-docs/blob/master/rest-api_CN.md

查看所有货币对价格
	https://api.binance.com/api/v3/ticker/price
查看指定货币对价格
	https://api.binance.com/api/v3/ticker/price?symbol={symbol_name}
例如查看 BTCUSDT
	https://api.binance.com/api/v3/ticker/price?symbol=BTCUSDT