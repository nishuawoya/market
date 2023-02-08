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
            "txHash":"0xc43293159cea1ba0c711c51aa40094893c087412fa52addde10b5e3d7f983392",
            "identifier":"ETH",
            "partnerId":"1",
            "productId":"167",
            "payContractAddress":"0xeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeee",
            "payContractSymbol":"ETH",
            "payAmount":0.001,
            "buyUserAddress":"0xed69c7a8bffc861d3d818ccd41427a01c336f8b2",
            "partnerIncomeAddress":"0xeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeee",
            "systemIncomeAddress":"0x165a57869231636176c25d0eef1a8b2cc73ab209",
            "ratio":0.5,
            "time":"2023-02-08 15:48:43"
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
    "txHash":"0xc43293159cea1ba0c711c51aa40094893c087412fa52addde10b5e3d7f983392",
    "identifier":"ETH",
    "partnerId":"1",
    "productId":"167",
    "payContractAddress":"0xeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeee",
    "payContractSymbol":"ETH",
    "payAmount":0.001,
    "buyUserAddress":"0xed69c7a8bffc861d3d818ccd41427a01c336f8b2",
    "partnerIncomeAddress":"0xeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeee",
    "systemIncomeAddress":"0x165a57869231636176c25d0eef1a8b2cc73ab209",
    "ratio":0.5,
    "time":"2023-02-08 15:48:43"
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

**响应**
```javascript
    # Response
{
    "code":1,
    "message":"ok",
    "result":null
}
```