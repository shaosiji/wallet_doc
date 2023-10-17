
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
lang |STRING| NO |语言信息。默认不传为 zh-CN(中文),英文为 en|

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
symbol |STRING | NO | 查看指定的交易对，多个交易对之间用逗号隔开,如果不传参表示查看所有交易对，例:如果我想查看BTC价格，传递的参数应该是BTCUSDT,现在支持传单个币，比如BTC，但是会默认查询BTCUSDT |	

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
address |STRING | YES | 钱包地址 |
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
                "cross_chain_name": "",                //跨链名称
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
symbol |STRING | NO | 币种信息，btc比特币,noc nova,eth 以太币,不传值表示查询所有币种 |


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

### 获取dapp所有分组


```
GET /api/v1/dapptypes
```
**参数:**
名称 | 类型 | 是否必须 | 描述
------------ | ------------ | ------------ | ------------
page |INT | YES | page  页号从1开始 |
count |INT | YES | 每页数量 |
lang |STRING| NO |语言信息。默认不传为 zh-CN(中文),英文为 en|

**响应:**
```
{
    "code": 10000,
    "msg": "success",
    "data": {
        "pages": {
            "page": 1,
            "size": 10,
            "total": 1
        },
        "list": [
            {
                "type": "hot", //分组id
                "name": "热门" //分组名称
            },
            {
                "type": "new",
                "name": "新品"
            },
            {
                "type": "nft",
                "name": "NFT"
            },
            {
                "type": "bsc",
                "name": "BSC"
            },
            {
                "type": "defi",
                "name": "DeFi"
            },
            {
                "type": "polygon",
                "name": "polygon"
            }
        ]
    }
}

```

-------------------------------------------------------------------------------------------

### 根据分组id返回相应的dapp


```
GET /api/v1/dapps
```
**参数:**
名称 | 类型 | 是否必须 | 描述
------------ | ------------ | ------------ | ------------
page |INT | YES | page  页号从1开始 |
count |INT | YES | 每页数量 |
type |STRING | YES | 分组id | 


**响应:**
```
{
    "code": 10000,
    "msg": "success",
    "data": {
        "pages": {
            "page": 1,
            "size": 10,
            "total": 1
        },
        "list": [
            {
                "type": "bsc",  //分组id
                "name": "bsc1", //dapp名称
                "url": "https://mempool.space/", //dapp地址
                "icon": "https://hk.tpstatic.net/token/tokenpocket-1654746200716.png", //dapp icon地址
                "remark": "薄饼app"                                                   //描述信息
            },
            {
                "type": "bsc",
                "name": "bsc2",
                "url": "https://mempool.space/",
                "icon": "https://hk.tpstatic.net/token/tokenpocket-1654746200716.png",
                "remark": "薄饼app"
            }
        ]
    }
}

```
-------------------------------------------------------------------------------------------
###查看市场分组

```
GET /api/v1/marketclass
```

**参数:**
	
名称 | 类型 | 是否必须 | 描述
------------ | ------------ | ------------ | ------------
lang |STRING| NO |语言信息。默认不传为 zh-CN(中文),英文为 en|


**响应:**

```	
	{
        "code": 10000,
        "msg": "success",
        "data": {
            "pages": {
                "page": 1,
                "size": 10,
                "total": 1
            },
            "list": [
                {
                    "class": "hot",  //分组名称
                    "title": "热门" //显示名称
                },
                {
                    "class": "gainers",
                    "title": "涨幅榜"
                },
                {
                    "class": "losers",
                    "title": "跌幅榜"
                },
                {
                    "class": "meme",
                    "title": "Meme"
                },
                {
                    "class": "Arb",
                    "title": "Arb"
                },
                {
                    "class": "OP",
                    "title": "OP"
                },
                {
                    "class": "defi",
                    "title": "DeFi"
                },
                {
                    "class": "nft",
                    "title": "NFT"
                },
                {
                    "class": "gamefi",
                    "title": "GameFi"
                },
                {
                    "class": "metaverse",
                    "title": "Metaverse"
                }
            ]
        }
    }

```
-------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------
###查看市场币种价格,24小时内

```
GET /api/v1/marketlist
```

**参数:**
	
名称 | 类型 | 是否必须 | 描述
------------ | ------------ | ------------ | ------------
class |STRING | YES | 分组id，默认为hot |	
lang |STRING| NO |语言信息。默认不传为 zh-CN(中文),英文为 en|

**响应:**

```{
       "code": 10000,
       "msg": "success",
       "data": {
           "pages": {
               "page": 1,
               "size": 50,
               "total": 1
           },
           "list": [
               {
                   "blockchain_id": 1,
                   "address": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
                   "chain_id": "ETH",                   //网络id
                   "icon": "https://hk.tpstatic.net/token/tokenpocket-1617349051539.png",   //图标
                   "name": "Wrapped Ether",             //token名称
                   "symbol": "ETH",                     //token符号
                   "status": 0,
                   "pair": "0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640",
                   "price_usd": 1645.752200486269,      //当前价格
                   "volume": 157572816.219058,          //交易量
                   "chg": 0.0046                        //改变区间，如果要显示百分比需要乘以100
               },
               {
                   "blockchain_id": 24,
                   "address": "0x82af49447d8a07e3bd95bd0d56f35241523fbab1",
                   "chain_id": "ARB",
                   "icon": "https://hk.tpstatic.net/token/tokenpocket-1617349051539.png",
                   "name": "Wrapped Ether",
                   "symbol": "ETH",
                   "status": 0,
                   "pair": "0xc31e54c7a869b9fcbecc14363cf510d1c41fa443",
                   "price_usd": 1644.3167717528374,
                   "volume": 29448748.241987,
                   "chg": 0.0049
               }
           ]
       }
   }

```
-------------------------------------------------------------------------------
###根据币种查看查看价格

```
GET /api/v1/prices
```

**参数:**
	
名称 | 类型 | 是否必须 | 描述
------------ | ------------ | ------------ | ------------
symbol |STRING | YES | 查看指定的交易对，多个交易对之间用逗号隔开,如果不传参表示查看所有交易对，例:如果我想查看BTC价格，传递的参数应该是BTCUSDT,现在支持传单个币，比如BTC，但是会默认查询BTCUSDT |	


**响应:**

```{
   	"code": 10000,
   	"msg": "success",
   	"data": {
   		"pages": {
   			"page": 1,
   			"size": 4,
   			"total": 1
   		},
   		"list": [{
   			"symbol": "USDT",               //名称
   			"price": "0.9994345897574524" //价格
   		}, {
   			"symbol": "ETH",
   			"price": "1852.6989484569144"
   		}, {
   			"symbol": "BTC",
   			"price": "0"
   		}, {
   			"symbol": "TRX",
   			"price": "0.0792033467730213"
   		}]
   	}
   }

```
-------------------------------------------------------------------------------

###查看自选市场

```
GET /api/v1/marketself
```

**参数:**
 无

**响应:**

```{
       "code": 10000,
       "msg": "success",
       "data": {
           "pages": {
               "page": 1,
               "size": 50,
               "total": 1
           },
           "list": [
               {
                   "blockchain_id": 1,
                   "address": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
                   "chain_id": "ETH",                   //网络id
                   "icon": "https://hk.tpstatic.net/token/tokenpocket-1617349051539.png",   //图标
                   "name": "Wrapped Ether",             //token名称
                   "symbol": "ETH",                     //token符号
                   "status": 0,
                   "pair": "0x88e6a0c2ddd26feeb64f039a2c41296fcb3f5640",
                   "price_usd": 1645.752200486269,      //当前价格
                   "volume": 157572816.219058,          //交易量
                   "chg": 0.0046                        //改变区间，如果要显示百分比需要乘以100
               },
               {
                   "blockchain_id": 24,
                   "address": "0x82af49447d8a07e3bd95bd0d56f35241523fbab1",
                   "chain_id": "ARB",
                   "icon": "https://hk.tpstatic.net/token/tokenpocket-1617349051539.png",
                   "name": "Wrapped Ether",
                   "symbol": "ETH",
                   "status": 0,
                   "pair": "0xc31e54c7a869b9fcbecc14363cf510d1c41fa443",
                   "price_usd": 1644.3167717528374,
                   "volume": 29448748.241987,
                   "chg": 0.0049
               }
           ]
       }
   }

```
-------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------

### 返回版本更新信息

```
GET /api/v1/versions
```


参数
	
名称 | 类型 | 是否必须 | 描述
------------ | ------------ | ------------ | ------------
page |INT | YES | page  页号从1开始 |
count |INT | YES | 每页数量 |	
lang |STRING| NO |语言信息。默认不传为 zh-CN(中文),英文为 en|
type |STRING| YES |app类型。android表示安卓，ios表示苹果|

**响应:**
	
	{
        "code": 10000,
        "msg": "success",
        "data": {
            "pages": {
                "page": 1,
                "size": 10,
                "total": 1
            },
            "list": [
                {
                    "id": 2,
                    "url": "https://d.nut-storage.com/downloads/apk/app-release.apk",   //链接地址
                    "title": "v1.0.12更新",                               //标题
                    "txt": "see more at http://<p><br></p>",                //内容
                    "version_no": "1.0.2",                              //版本号
                    "type": "android",
                    "CreateTime": "",
                    "UpdateTime": "",
                    "LangCode": "",
                    "is_force": 0                                       //是否强制更新 0表示不是 1表示是
                }
            ]
        }
    }

-------------------------------------------------------------------------------------------

### 波场签名

```
POST /api/v2/tronsign
```
参数  

```
{
    "tx":{}, //transaction由 createtransaction返回的参数
    "prikey":""//密钥 用 AES-256
}
```
	

**响应:**
```
{
    "code": 10000,
    "message": "ok",
    "data": {
        "signature": [  //签名信息
            "964763dede052fd0973f6cb9f8a8bbab6234d7fc916fcf5e66a2a163e8bf5bd006251f76726cd59b98b4ccf9992fd66510605936db7e84e6cb1f32c052af7f641B"
        ]
    }
}
```
-------------------------------------------------------------------------------------------

### 波场创建智能合约

```
POST /api/v2/createtransfer
```
参数  

```
{
    "contractAddress":"TDk91SWz2GvwfZwMTGX21d4ngUUH8YZZAv", //合约地址
    "toAddress":"TUbQqrynqJXCMSSTCxKavspWTyWHE8edhd",		//接收地址
    "amount":1												//金额
}
```
	

**响应:**
```
{
    "code": 10000,
    "message": "ok",
    "data": { //data就是transaction，用这个去做签名 和广播
        "visible": false,
        "txID": "c3ecdb60a039684c93ccbc7bdee738ef8d6f2217ad652f366e5850f8f8ace158",
        "raw_data": {
            "contract": [
                {
                    "parameter": {
                        "value": {
                            "data": "a9059cbb000000000000000000000000cc4b1f9ba729d82ce9c317f6bfd1fdbe497ae7cf0000000000000000000000000000000000000000000000000000000000000001",
                            "owner_address": "41cc4b1f9ba729d82ce9c317f6bfd1fdbe497ae7cf",
                            "contract_address": "412967c318a01cb50eb1f5bb99943b01012ad758f1"
                        },
                        "type_url": "type.googleapis.com/protocol.TriggerSmartContract"
                    },
                    "type": "TriggerSmartContract"
                }
            ],
            "ref_block_bytes": "4ff6",
            "ref_block_hash": "ac23793feac20585",
            "expiration": 1695449850000,
            "fee_limit": 150000000,
            "timestamp": 1695449792821
        },
        "raw_data_hex": "0a024ff62208ac23793feac205854090c1be85ac315aae01081f12a9010a31747970652e676f6f676c65617069732e636f6d2f70726f746f636f6c2e54726967676572536d617274436f6e747261637412740a1541cc4b1f9ba729d82ce9c317f6bfd1fdbe497ae7cf1215412967c318a01cb50eb1f5bb99943b01012ad758f12244a9059cbb000000000000000000000000cc4b1f9ba729d82ce9c317f6bfd1fdbe497ae7cf000000000000000000000000000000000000000000000000000000000000000170b582bb85ac31900180a3c347"
    }
}
```
-------------------------------------------------------------------------------------------

### 比特币转换地址

```
POST /api/v2/bitconinp2sh
```
参数  

```
{
    "prikey":""//密钥 用 AES-256									
}
```
	

**响应:**
```
{
   {
       "code": 10000,
       "message": "ok",
       "data": "31w2nwgBW6Q9diHAFLsXwunbRQnMY45U2p" //转换后地址
   }
}
```
-------------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------------

### 比特币hash交易

```
POST /api/v2/bithash
```
参数  

```
{
    "prikey":"",//私钥必须经过加密
    "to":"31w2nwgBW6Q9diHAFLsXwunbRQnMY45U2p",//接收地址
    "value":"10" //金额，以聪为单位
}
```
	

**响应:**
```
{
    "code": 10000,
    "message": "ok",
    //data hash值，获得hash值后直接推送
    "data": "020000000001011044f69a6e48a95d55751a7ec7dc6918b90a2974e2dcf3ad323fb74d74a5536c0000000017160014be49946a3585c2c5e966e3583b52d2e8471d92d9ffffffff010a0000000000000017a91402a68c809934ef238e1d3359748a8b0579b45096870247304402204d6383a1c0fca107c89569982f47fc71075a55ba3ab85d845c188eb7518f22bc02202874134df7fc9d7dda076a4697020a255602be36be74a6146917c894faf71d2c01210250466a227ddc68499fd98e2912fb9cc032eb0fe1103a57b7b308364cea3e498100000000"
}
```
-------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------

### 波场兑换token

```
POST /api/v2/tronswap
```
参数  

```

{
    "prikey":""                                         //私钥必须经过加密
    ,"amount":"1300000"                                //转出token的金额
    ,"from_token":"TR7NHqjeKQxGTCi8q8ZY4pL8otSzgjLj6t" //转出token
    ,"to_token":"THb4CqiFdwNHsWsQCs4JhzwjMWys4aqCbF"   //转入token
    ,"limit":75000000                                  //交易费用 包括授权费用
}
```
	

**响应:**
```
{
    "code": 10000,
    "message": "ok",
    "data": "" //返回的交易hash 用于查账
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