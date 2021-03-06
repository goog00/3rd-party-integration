## 订单同步
### 1.订单批量查询
#### 1.1 接口描述
> 系统方提供本接口供商户方查询
#### 1.2 请求方式
> POST
#### 1.3 url
> /offline/tradesList
#### 1.4 数据方向
> 系统方至商户方
#### 1.5 请求参数
| 参数名称 | 参数类型 | 是否必须 | 示例值 | 参数描述  |
| :---         |     :---      |     :--- | :--- | :--- |
| sTime   | 字符串     | 否    | "2017-07-01 12:22:12"    | 订单开始时间(按创建时间) |
| eTime   | 字符串    | 否    | "2017-07-01 12:22:12"    | 订单结束时间(按创建时间) |
| type   | 整形     | 否    | 0   |1:已付款;0:已退款|
| pageNum   | 整形    | 否    | 1   | 分页参数，第1页（数据较多时，默认分页返回）|
| pageSize   | 整形     | 否    | 15   | 分页数据，每页显示数据条数 |
--------------------- 
#### 1.6 返回示例(请求成功)
 ``` 
{
  "msg": "订单查询成功",
  "total": 49813,//订单总数量
  "code": 0,//0:成功，-1：失败
  "tradesList": [
    {
      "realPay": 180,//实付款
      "receiverName": "黎正华",//收货人姓名
      "mobile": "17633702820",//收货人手机号码
      "postFee": 0,//运费
      "orderList": [//商品列表
        {
          "gprice": 100,//商品价格
          "gsc": "10mg*100s",//商品规格
          "gcode": "32301029",//商品编码
          "gnum": 1//购买数量
        }
      ],
      "discount": 0,//优惠金额
      "paystyle": "wx",//支付方式:ali (支付宝) ，wx (微信)， bil(快钱)， unionPay(银联)， health_insurance（医保），cash（现金）
      "poststyle": 170,//购买方式，150：送货上门；160：门店自提；170：门店直购
      "tId": 1001661501752197580,//订单编号
      "uid": "123",//门店编码
      "totalPay": 180,//商品金额+运费
      "totalFee": 180,//商品金额
      "createTime": "2017-08-03 17:23:17",//订单创建时间
      "receicerAddress": "",//收货地址
      "memberMobile": "17633702820",//会员手机号码
      "status": 1//订单状态：1：已付款（未退款），0：已退款
    },
  ]
}
```
#### 1.7 返回示例(请求失败)
```
{
  "code": -1,
  "info": [],
  "msg":"请求失败"
}
```
