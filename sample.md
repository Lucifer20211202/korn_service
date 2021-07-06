## 全市场的完整 Ticker

所有 symbol 24 小时完整 ticker 信息.需要注意的是,只有发生变化的 ticker 更新才会被推送。

> https://binance-docs.github.io/apidocs/delivery/cn/#ticker-2

接口返回定义

```json
[
  {
    "e": "24hrTicker", // 事件类型
    "E": 1591268262453, // 事件时间
    "s": "BTCUSD_200626", // 交易对
    "ps": "BTCUSD", // 标的交易对
    "p": "-43.4", // 24小时价格变化
    "P": "-0.452", // 24小时价格变化(百分比)
    "w": "0.00147974", // 24小时平均价格
    "c": "9548.5", // 最新成交价格
    "Q": "2", // 最新成交价格上的成交量
    "o": "9591.9", // 24小时前第一笔成交价格
    "h": "10000.0", // 24小时内最高成交价
    "l": "7000.0", // 24小时内最低成交价
    "v": "487850", // 24小时成交量
    "q": "32968676323.46222700", // 24小时成交额(标的数量)
    "O": 1591181820000, // 统计开始时间
    "C": 1591268262442, // 统计关闭时间
    "F": 512014, // 24小时内第一笔成交交易ID
    "L": 615289, // 24小时内最后一笔成交交易ID
    "n": 103272 // 24小时内成交数
  }
]
```

## K 线数据

每根 K 线的开盘时间可视为唯一 ID

> https://dapi.binance.com/dapi/v1/klines > https://binance-docs.github.io/apidocs/delivery/cn/#k

年 > 1 天(1d) > 365
月 > 2 小时(2h) > 30 _ 12 = 360
周 > 半小时(30m) > 7 _ 24 _ 2 = 336
天 > 5 分钟(5m) > 24 _ 12 = 288

```bash
http get https://dapi.binance.com/dapi/v1/klines symbol==BTCUSD_210625 interval==5m limit==100 endTime==1619774613000
```