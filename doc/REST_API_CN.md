应用市场 接口文档
==================================================
- [获取购买记录](#获取购买记录)
- [上报购买记录](#上报购买记录)


# 获取购买记录
分页获取购买记录列表

###  请求方式
get

###  请求示例
https://api.gopluseco.io/api/v1/market/buy?partnerId=1&chain=ETH&pageNum=1&pageSize=2

###  参数
| 参数名 | 参数类型  | 必填 | 描述 |
| ------------- |----|----|----|
| partnerId | String | 是 | 合作商id |
| chain | String | 是 | 链 如ETH、BSC |
| pageNum | int | 是 | 第几页 |
| pageSize | int | 是 | 每页多少条 |

**响应**
```javascript
    # Response
{
    "code":1,
    "message":"ok",
    "result":{
        "totalCount":5,
        "list":[
        {
            "txHash": "0x2f6ff9d339c1040dd717882a0fb9a9d7bfb2b8104fe03be6adf4f6bba5bb415a",
            "identifier": "ETH",
            "partnerId": "1",
            "productId": "167",
            "payContractAddress": "0x8d8bad32025076acfd59f030f162ab075c58b7cc",
            "payContractSymbol": "USDT",
            "payAmount": 9.9000000000000000,
            "buyUserAddress": "0x5ff8e5c3f5a318ed8c68423aa78d77f922b38f19",
            "partnerIncomeAddress": "0xf12a705969474175fc984d7d24a428294ce01a81",
            "systemIncomeAddress": "0x165a57869231636176c25d0eef1a8b2cc73ab209",
            "ratio": 0.7000,
            "time": "2023-04-14 01:20:04",
            "buyDays": 1,
            "expiresTime": 1684165524,
            "isAuto": "Y",
            "autoPayStop": "N"
        }
    ]
}
}
```

**返回值说明**

|返回字段|字段说明|
|--------| :-------: |
|txHash| 交易hash |
|identifier| 链 |
|partnerId| 合作商id |
|productId| 商品id |
|payContractAddress| 支付合约地址 0xeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeee为主链币|
|payContractSymbol| 支付合约币种 |
|payAmount| 支付数量 |
|buyUserAddress| 购买地址 |
|partnerIncomeAddress| 合作商收款地址 |
|systemIncomeAddress| 系统收款地址 |
|ratio| 分成比例 |
|time| 交易时间 |
|buyDays| 购买天数 |
|expiresTime| 过期时间 |
|isAuto| 是否自动续费 |
|autoPayStop| 停止自动续费 |



# 上报购买记录

###  请求域名
有项目方提供

###  请求路径
/buy-record

###  请求方式
post

###  参数
```javascript
{
    "txHash": "0x2f6ff9d339c1040dd717882a0fb9a9d7bfb2b8104fe03be6adf4f6bba5bb415a",
        "identifier": "ETH",
        "partnerId": "1",
        "productId": "167",
        "payContractAddress": "0x8d8bad32025076acfd59f030f162ab075c58b7cc",
        "payContractSymbol": "USDT",
        "payAmount": 9.9000000000000000,
        "buyUserAddress": "0x5ff8e5c3f5a318ed8c68423aa78d77f922b38f19",
        "partnerIncomeAddress": "0xf12a705969474175fc984d7d24a428294ce01a81",
        "systemIncomeAddress": "0x165a57869231636176c25d0eef1a8b2cc73ab209",
        "ratio": 0.7000,
        "time": "2023-04-14 01:20:04",
        "buyDays": 1,
        "expiresTime": 1684165524,
        "isAuto": "Y",
        "autoPayStop": "N"
}
```
**请求参数说明**

|返回字段|字段说明|
|--------| :-------: |
|txHash| 交易hash  通过txHash做唯一索引，支持重复上报|
|identifier| 链 |
|partnerId| 合作商id |
|productId| 商品id |
|payContractAddress| 支付合约地址 0xeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeee为主链币|
|payContractSymbol| 支付合约币种 |
|payAmount| 支付数量 |
|buyUserAddress| 购买地址 |
|partnerIncomeAddress| 合作商收款地址 |
|systemIncomeAddress| 系统收款地址 |
|ratio| 分成比例 |
|time| 交易时间 |
|buyDays| 购买天数 |
|expiresTime| 过期时间 |
|isAuto| 是否自动续费 |
|autoPayStop| 停止自动续费 |

**响应**
```javascript
    # Response
{
    "code":1,
    "message":"ok",
    "result":null
}
```