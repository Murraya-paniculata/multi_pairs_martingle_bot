# 51bitquant-multi_pairs_martingle_bot
A muti pairs martingle trading bot for Binance exchange. 

多个交易对的马丁格尔策略。可以在币安上交易现货或者合约。

## 配置文件

```
 {
  "platform": "binance_future",
  "api_key": "xxxx",
  "api_secret": "xxxxx",
  "max_pairs": 4,
  "pump_pct": 0.03,
  "initial_trade_value": 500,
  "trade_value_multiplier": 1.3,
  "increase_pos_when_drop_down": 0.05,
  "exit_profit_pct": 0.01,
  "profit_pull_back_pct": 0.01,
  "trading_fee": 0.0004,
  "max_increase_pos_count": 5,
  "proxy_host": "",
  "proxy_port": 0
}

```
配置文件的参数说明。

1. platform: 可选的值有两个,分别是binance_future和binance_spot，
   如果你想交易现货，就填写binance_spot, 合约就写binance_future
2. api_key: 币安交易所的api key
3. api_secret: 币安交易所的api secret
4. max_pairs: 交易对的最大数量，如果你想同时持仓10个交易对，那么这里就写10.
5. pump_pct: 小时线暴涨百分之多少后入场,
   当然你可以修改源码，修改你的入场逻辑。这个策略的思路是挑选小时暴涨的币，然后用马丁格尔的策略去交易。
6. initial_trade_value: 每个交易对的初始交易金额
7. increase_pos_when_drop_down: 回调多少后加仓。

8. exit_profit_pct: 出场点位

9. profit_pull_back_pct: 最高值回调多少后，且有利润的时候才出场.

10. trading_fee: 交易的资金费率。
 
11. max_increase_pos_count: 最大的加仓次数.
    
12. turnover_threshold:
    这个是过滤值，就是要求一小时的最低成交量不能低于多少，默认是值 100,000 USDT.
13. blocked_lists:
    这个是禁止交易的交易对，如果你想过滤某写不想交易的山寨币，你可以把他们放在这个列表上如:
    ['XMLUSDT', 'XRPUSDT'],
    
14. allowed_lists: 如果你只想交易某一些交易对，那么放这里:
    ['BTCUSDT', 'ETHUSDT', 'ADAUSDT', 'BNBUSDT']

15. proxy_host: 代理主机ip地址： 如'132.148.123.22'

16. proxy_port: 代理主机的端口号如: 8888, 9999 ect.


## 如何使用
1. 把代码下载下来，然后编辑config.json文件，它会读取你这个配置文件，记得填写你的交易所的api
   key 和 secret, 然后保存该配置文件，配置文件选项的说明如上面描述。
2. 直接运行main.py文件或者通过shell脚本运行, 执行 sh start.sh 就可以运行。


## 联系我
如果关于代码任何有问题，可以提交issues, 或者联系我微信: bitquant51



