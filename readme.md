
# 区块链名称对应关系

	BSC-HD 币安BSC链

	ETH-HD 以太坊主链

# 请求地址

### 主域名
```
    https://bakewallet.io 
```

### 备用域名
```
    https://bakewallet.pro 
```

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

错误码参见 

https://github.com/shaosiji/wallet_doc/blob/main/errorcode.md

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
chain_id |STRING | YES | 区块链id |	 
	
**响应:**
```	
	{
		"code": 10000,
		"msg": "success",
		"data": {
            "pages":{
               "page": 20,//页号
               "size": 1,//每页数量
               "total": 1//最大页数
            },		
			"list": [{
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
				"from_addr": "0x277d9d29c6ec9f89adeec153d96e273dab753eb6",		//转出地址
				"to_addr": "0x96ecced577d48850017d883e1cb543418da85702",		//转入地址
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
chain_id |STRING | YES | 区块链id |	

**响应:**
```
{
	"code": 10000,
	"msg": "success",
	"data": {
        "pages":{
           "page": 20,//页号
           "size": 1,//每页数量
           "total": 1//最大页数
        },	
		"list": [{
			"hid": 899734962,
			"blockchain_id": 1,	//区块链id
			"blockchain": null,
			"name": "HarryPotterObamaPacMan8Inu",
			"symbol": "XRP",	//token名称
			"bl_symbol": "XRP",	//token符号
			"gas": 60000,		//gas费用
			"decimal": 8,
			"precision": 8,
			"balance": "",
			"price_usd": 0.2489487047716612,
			"percent_change_24h": 0,
			"asset": 0,
			"added": 0,
			"address": "0x07e0edf8ce600fb51d44f51e3348d77d67f298ae",  //合约地址
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
			"icon_url": "https://hk.tpstatic.net/token/tokenpocket-1692428812431.png",  //
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
        "pages":{
           "page": 20,//页号
           "size": 1,//每页数量
           "total": 1//最大页数
        },	
		"list": [{
			"title": "新app上架了",	//标题
			"image_url": "http://image.com",	//图片地址
			"jump_url": "http://jump.com",		//跳转url
			"type": 0,
			"txt": "测试内容"					//内容
		}]
	}
}

-------------------------------------------------------------------------------------------

###查看公告

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
        "pages":{
           "page": 20,//页号
           "size": 1,//每页数量
           "total": 1//最大页数
        },	
		"list": [{
			"title": "2023-08-30 update version",		//标题
			"type": 0,
			"txt": "see more at http://",				//内容
			"image_url": "http://"						//图片地址
		}]
	}
}

-------------------------------------------------------------------------------------------

###查看rpc节点

```
GET /api/v1/rpcnodes
```

**参数:**
	
名称 | 类型 | 是否必须 | 描述
------------ | ------------ | ------------ | ------------
page |INT | YES | page  页号从1开始 |
count |INT | YES | 每页数量 |
chain_id |STRING | YES | 区块链id |	

**响应:**

```	
	{
	"code": 10000,
	"msg": "success",
	"data": {
        "pages":{
           "page": 20,//页号
           "size": 1,//每页数量
           "total": 1//最大页数
        },	
		"list": [{
			"chain_id": "ETH-HD",			//区块链名称
			"chain_name": "以太坊节点1",	//节点名称
			"rpc_url": "https://rpc.ankr.com/eth",	//rpc节点
			"icon": "",								//图标
			"remark": " "
		}]
	}
}

```
-------------------------------------------------------------------------------
### 查看最新市场行情

```
GET /api/v1/marketnewest
```
**参数:**
	
名称 | 类型 | 是否必须 | 描述
------------ | ------------ | ------------ | ------------
symbol |STRING | NO | 查看指定的交易对，如果不传参表示查看所有交易对，例:如果我想查看BTC价格，传递的参数应该是BTCUSDT,现在支持传单个币，比如BTC，但是会默认查询BTCUSDT |	

**响应:**
```

{
	"code": 10000,
	"msg": "success",
	"data": {
        "pages":{
           "page": 20,//页号
           "size": 1,//每页数量
           "total": 1//最大页数
        },	
		"list": [{
			"symbol": "BTCUSDT",    //交易对
			"price": "27407.43000000" //交易价格
		}]
	}
}

```

-------------------------------------------------------------------------------

### 查看最近24小时场行情

```
GET /api/v1/market24hr
```
**参数:**
	
名称 | 类型 | 是否必须 | 描述
------------ | ------------ | ------------ | ------------
symbol |STRING | YES | 查看指定的交易对，多个交易对之间用逗号隔开,例:如果我想查看BTC价格，传递的参数应该是BTCUSDT,现在支持传单个币，比如BTC，但是会默认查询BTCUSDT |	

**响应:**
```

{
	"code": 10000,
	"msg": "success",
	"data": {
        "pages":{
           "page": 20,//页号
           "size": 1,//每页数量
           "total": 1//最大页数
        },	
		"list": [{
          "symbol":      "BNBUSDT",          // 交易对
          "openPrice":   "99.00000000",     // 间隔开盘价
          "highPrice":   "100.00000000",    // 间隔最高价
          "lowPrice":    "0.10000000",      // 间隔最低价
          "lastPrice":   "4.00000200",      // 间隔收盘价
          "volume":      "8913.30000000",   // 总交易量 (base asset)
          "quoteVolume": "15.30000000",     // 总交易量 (quote asset)
          "openTime":    1499783499040,     // ticker间隔的开始时间
          "closeTime":   1499869899040,     // ticker间隔的结束时间
          "firstId":     28385,             // 统计时间内的第一笔trade id
          "lastId":      28460,             // 统计时间内的最后一笔trade id
          "count":       76                 // 统计时间内交易笔数
        }]
	}
}

```

-------------------------------------------------------------------------------

### 获取所有区块链信息

```
GET /api/v1/chains
```
**参数:**
名称 | 类型 | 是否必须 | 描述
------------ | ------------ | ------------ | ------------
page |INT | YES | page  页号从1开始 |
count |INT | YES | 每页数量 |

**响应:**
```
{
    "code": 10000,
    "msg": "success",
    "data": {
        "pages":{
           "page": 20,//页号
           "size": 1,//每页数量
           "total": 1//最大页数
        },	
        "list": [
            {
                "id": "BTC-HD",             //区块链id
                "name": "Bitcoin",          //区块链名称
                "name_cn": "比特币",        //中文名
                "token_name": "BTC",        //token名称
                "token_sort_name": "BTC",   
                "remark": "",
                "icon": "",                //图标
                "nodes": [                  //rpc 节点列表
                    {
                        "chain_id": "BSC-HD",
                        "chain_name": "币按节点1",
                        "rpc_url": "https://fluent-bitter-choice.bsc.quiknode.pro/64183d52268ae88e00998a17b0d08033c1532d03/", //rpc 地址
                        "icon": "https://upload.wikimedia.org/wikipedia/commons/1/1c/BNB%2C_native_cryptocurrency_for_the_Binance_Smart_Chain.svg",
                        "remark": " "
                    },
                    {
                        "chain_id": "BSC-HD",
                        "chain_name": "币按节点2",
                        "rpc_url": "https://sparkling-fabled-patina.bsc.quiknode.pro/8a7493ea23005d46439da41759d19856ebb591f5/",
                        "icon": "https://upload.wikimedia.org/wikipedia/commons/1/1c/BNB%2C_native_cryptocurrency_for_the_Binance_Smart_Chain.svg",
                        "remark": " "
                    }
                ]
            }
        ]
    }
}

```
-------------------------------------------------------------------------------------------

### 获取在指定区块链上我添加的token信息

** 注意，如果本地添加的token没有任何交易记录，区块链上是查不到是否已经添加过这个token **

```
GET /api/v1/mytokens
```
**参数:**
名称 | 类型 | 是否必须 | 描述
------------ | ------------ | ------------ | ------------
page |INT | YES | page  页号从1开始 |
count |INT | YES | 每页数量 |
address |STRING | YES | 钱包地址 |
chain_id |STRING | YES | 区块链id |

**响应:**
```
{
    "code": 10000,
    "msg": "success",
    "data": {
        "pages":{
           "page": 20,//页号
           "size": 1,//每页数量
           "total": 1//最大页数
        },	
        "list": [
                {
                    "name": "Binance Smart Chain",  //全名
                    "symbol": "BNB",                //token名称
                    "bl_symbol": "BNB",
                    "contract_address": ""          //合约地址
                },
                {
                    "name": "Tether USD",
                    "symbol": "USDT",
                    "bl_symbol": "USDT",
                    "contract_address": "0x55d398326f99059ff775485246999027b3197955"     //合约地址
                }
        ]
    }
}

```

-------------------------------------------------------------------------------------------

###  查看所有币信息

```
GET /api/v1/coins
```

**参数:**
	
名称 | 类型 | 是否必须 | 描述
------------ | ------------ | ------------ | ------------
page |INT | YES | page  页号从1开始 |
count |INT | YES | 每页数量 |	

**响应:**

```	
	{
	"code": 10000,
	"msg": "success",
	"data": {
        "pages":{
           "page": 20,//页号
           "size": 1,//每页数量
           "total": 1//最大页数
        },	
		"list": [{
        			"id": "XRP",
        			"name": "XRP",
        			"name_cn": "瑞波币",
        			"symbol": "XRP",
        			"icon": "https://www.clipartmax.com/png/middle/35-359666_ripple-kurs-live-in-euro-und-dollar-ripple-icon-png.png"
        		}, {
        			"id": "Bitcoin",
        			"name": "Bitcoin",
        			"name_cn": "比特币",
        			"symbol": "BTC",
        			"icon": "https://upload.wikimedia.org/wikipedia/commons/thumb/4/46/Bitcoin.svg/1280px-Bitcoin.svg.png"
        		}, {
        			"id": "BitcoinCash",
        			"name": "Bitcoin Cash",
        			"name_cn": "比特币现金",
        			"symbol": "BCH",
        			"icon": "https://cdn4.iconfinder.com/data/icons/crypto-currency-and-coin-2/256/bitcoincash_bch_bitcoin-1024.png"
        		}, {
        			"id": "BNB",
        			"name": "BNB",
        			"name_cn": "币安币",
        			"symbol": "BNB",
        			"icon": "https://seeklogo.com/images/B/binance-coin-bnb-logo-97F9D55608-seeklogo.com.png"
        		}, {
        			"id": "Dogecoin",
        			"name": "Dogecoin",
        			"name_cn": "狗狗币",
        			"symbol": "DOGE",
        			"icon": "https://pngimg.com/uploads/doge_meme/doge_meme_PNG20.png"
        		}, {
        			"id": "Ethereum",
        			"name": "Ethereum",
        			"name_cn": "以太坊",
        			"symbol": "ETH",
        			"icon": "https://cdn.pixabay.com/photo/2021/05/24/09/15/ethereum-6278326_1280.png"
        		}, {
        			"id": "Litecoin",
        			"name": "Litecoin",
        			"name_cn": "莱特币",
        			"symbol": "LTC",
        			"icon": "https://www.spectre.ai/assets/images/assets/LTC-logo.png"
        		}, {
        			"id": "Polygon",
        			"name": "Polygon",
        			"name_cn": "Polygon",
        			"symbol": "MATIC",
        			"icon": "https://assets-cdn.trustwallet.com/blockchains/polygon/info/logo.png"
        		}, {
        			"id": "TetherUSDt",
        			"name": "Tether USDt",
        			"name_cn": "泰达币",
        			"symbol": "USDT",
        			"icon": "https://icons.iconarchive.com/icons/cjdowner/cryptocurrency-flat/256/Tether-USDT-icon.png"
        		}, {
        			"id": "TRON",
        			"name": "TRON",
        			"name_cn": "波场币",
        			"symbol": "TRX",
        			"icon": "https://cryptologos.cc/logos/tron-trx-logo.png"
        		}, {
        			"id": "USDCoin",
        			"name": "USD Coin",
        			"name_cn": "USDC",
        			"symbol": "USDC",
        			"icon": "https://cryptologos.cc/logos/usd-coin-usdc-logo.png"
        	}]
	}
}

```

-------------------------------------------------------------------------------------------


附录 

市场行业 币安公开的接口 无需认证 

币安文档接口地址 

https://github.com/binance/binance-spot-api-docs/blob/master/rest-api_CN.md

查看所有货币对价格
	https://api.binance.com/api/v3/ticker/price
查看指定货币对价格
	https://api.binance.com/api/v3/ticker/price?symbol={symbol_name}
例如查看 BTCUSDT
	https://api.binance.com/api/v3/ticker/price?symbol=BTCUSDT