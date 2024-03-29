# t(:marketdata)
t(:market_para_auth)

### t(:orderbook)
> t(:codequote_curlExample)

```console
curl https://openapi-testnet.zoomex.com/public/v1/orderBook?symbol=BTCUSD
```

```python
from pyzmx import inverse_perpetual
session_unauth = inverse_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com"
)
print(session.orderbook(symbol="BTCUSD"))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": [
        {
            "symbol": "BTCUSD",
            "price": "9487",
            "size": 336241,
            "side": "Buy"
        },
        {
            "symbol": "BTCUSD",
            "price": "9487.5",
            "size": 522147,
            "side": "Sell"
        }
    ],
    "time_now": "1567108756.834357"
}
```

t(:market_para_orderbook)

<aside class="notice">
t(:market_aside_orderbook)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpoL2>/public/v1/orderBook</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoL2"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_symbol) |string |t(:row_comment_symbol) |
| t(:row_parameter_price) |string |t(:row_comment_resp_price) |
| size |integer |t(:row_comment_resp_size) |
|t(:row_parameter_side) |string |t(:row_comment_side)  |


### t(:querykline)
> t(:codequote_curlExample)

```console
curl https://openapi-testnet.zoomex.com/public/v1/kline/list/inverse?symbol=BTCUSD&interval=1&limit=2&from=1581231260
```

```python
from pyzmx import inverse_perpetual
session_unauth = inverse_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com"
)
print(session_unauth.query_kline(
    symbol="BTCUSD",
    interval="D",
    from_time="1653408000"
))
```


> t(:codequote_responseExample)

```javascript
{
	"ret_code": 0,
	"ret_msg": "OK",
	"ext_code": "",
	"ext_info": "",
	"result": [{
		"symbol": "BTCUSD",
		"interval": "1",
		"open_time": 1581231300,
		"open": "10112.5",
		"high": "10112.5",
		"low": "10112",
		"close": "10112",
		"volume": "75981",
		"turnover": "7.51394369"
	}, {
		"symbol": "BTCUSD",
		"interval": "1",
		"open_time": 1581231360,
		"open": "10112",
		"high": "10112.5",
		"low": "10112",
		"close": "10112",
		"volume": "24616",
		"turnover": "2.4343353100000003"
	}],
	"time_now": "1581928016.558522"
}
```

t(:market_para_querykline)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpkList>/public/v1/kline/list/inverse</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpkList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|<a href="#kline-interval-interval">interval</a> |<b>true</b> |string |t(:row_comment_interval) |
|from |<b>true</b> |integer |t(:row_comment_from_timestamp) |
|limit |false |integer |t(:row_comment_limit_200) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_symbol) |string |t(:row_comment_symbol) |
| <a href="#kline-interval-interval">interval</a> |string |t(:row_comment_interval) |
| open_time |integer |t(:row_comment_resp_open_time) |
| open |string |t(:row_comment_open) |
| high |string |t(:row_comment_high) |
| low |string |t(:row_comment_low) |
| close |string |t(:row_comment_close) |
| volume |string |t(:row_comment_resp_volume) |
| turnover |string |t(:row_comment_resp_turnover) |

### t(:latestsymbolinfo)
> t(:codequote_curlExample)

```console
curl https://openapi-testnet.zoomex.com/public/v1/tickers
```

```python
from pyzmx import inverse_perpetual
session_unauth = inverse_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com"
)
print(session_unauth.latest_information_for_symbol(
    symbol="BTCUSD"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "result": [
        {
            "symbol": "BTCUSD",
            "bid_price": "19244.5",
            "ask_price": "19245",
            "last_price": "19244.50",
            "last_tick_direction": "MinusTick",
            "prev_price_24h": "18780.50",
            "price_24h_pcnt": "0.024706",
            "high_price_24h": "19582.00",
            "low_price_24h": "18492.50",
            "prev_price_1h": "19217.00",
            "mark_price": "19242.60",
            "index_price": "19229.37",
            "open_interest": 4.13999123e+08,
            "countdown_hour": 0,
            "turnover_24h": "1977.97821021",
            "volume_24h": 3.7810482e+07,
            "funding_rate": "0.0001",
            "predicted_funding_rate": "",
            "next_funding_time": "2022-09-08T16:00:00Z",
            "predicted_delivery_price": "",
            "total_turnover": "",
            "total_volume": 0,
            "delivery_fee_rate": "",
            "delivery_time": "",
            "price_1h_pcnt": "",
            "open_value": ""
        }
    ],
    "ext_code": "",
    "ext_info": "",
    "time_now": "1662629551.232415"
}
```

t(:market_para_symbol)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpTickers>/public/v1/tickers</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpTickers"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |false |string |t(:row_comment_symbol) |



<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_symbol) |string |t(:row_comment_symbol) |
| bid_price |string |t(:row_comment_resp_bid_price) |
| ask_price |string |t(:row_comment_resp_ask_price) |
| last_price |string |t(:row_comment_resp_last_price) |
|<a href="#tick-direction-type-tick_direction">last_tick_direction</a> |string |t(:row_comment_position_tick_direction) |
| prev_price_24h |string |t(:row_comment_resp_prev_price_24h) |
| price_24h_pcnt |string |t(:row_comment_resp_price_24h_pcnt) |
| high_price_24h |string |t(:row_comment_resp_high_price_24h) |
| low_price_24h |string |t(:row_comment_resp_low_price_24h) |
| prev_price_1h |string |t(:row_comment_resp_prev_price_1h) |
| price_1h_pcnt |string |t(:row_comment_resp_price_1h_pcnt) |
| mark_price |string |t(:row_comment_resp_mark_price) |
| index_price |string |t(:row_comment_resp_index_price) |
| open_interest |number |t(:row_comment_resp_open_interest) |
| open_value |string |t(:row_comment_resp_open_value) |
| total_turnover |string |t(:row_comment_resp_total_turnover) |
| turnover_24h |string |t(:row_comment_resp_turnover_24h) |
| total_volume |number |t(:row_comment_resp_total_volume) |
| volume_24h |number |t(:row_comment_resp_volume_24h) |
| funding_rate |string |t(:row_comment_resp_funding_rate) |
| predicted_funding_rate |string |t(:row_comment_resp_predicted_funding_rate) |
| next_funding_time |string |t(:row_comment_resp_next_funding_time) |
| countdown_hour |number |t(:row_comment_resp_countdown_hour) |
| delivery_fee_rate |string |t(:row_comment_resp_delivery_fee_rate) |
| predicted_delivery_price |string |t(:row_comment_resp_predicted_delivery_price) |
| delivery_time |string |t(:row_comment_resp_delivery_time) |


### t(:querysymbol)
> t(:codequote_curlExample)

```console
curl https://openapi-testnet.zoomex.com/public/v1/symbols
```

```python
from pyzmx import inverse_perpetual
session_unauth = inverse_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com"
)
print(session.query_symbol())
```


> t(:codequote_responseExample)

```javascript
{
    "ret_code":0,
    "ret_msg":"OK",
    "ext_code":"",
    "ext_info":"",
    "result":[
        {
            "name":"BTCUSD",
            "alias":"BTCUSD",
            "status":"Trading",
            "base_currency":"BTC",
            "quote_currency":"USD",
            "price_scale":2,
            "taker_fee":"0.00075",
            "maker_fee":"-0.00025",
            "funding_interval":480,
            "leverage_filter":{
                "min_leverage":1,
                "max_leverage":100,
                "leverage_step":"0.01"
            },
            "price_filter":{
                "min_price":"0.5",
                "max_price":"999999.5",
                "tick_size":"0.5"
            },
            "lot_size_filter":{
                "max_trading_qty":1000000,
                "min_trading_qty":1,
                "qty_step":1,
                "post_only_max_trading_qty":"5000000"
            }
        },
        {
            "name":"EOSUSD",
            "alias":"EOSUSD",
            "status":"Trading",
            "base_currency":"EOS",
            "quote_currency":"USD",
            "price_scale":3,
            "taker_fee":"0.00075",
            "maker_fee":"-0.00025",
            "funding_interval":480,
            "leverage_filter":{
                "min_leverage":1,
                "max_leverage":50,
                "leverage_step":"0.01"
            },
            "price_filter":{
                "min_price":"0.001",
                "max_price":"1999.999",
                "tick_size":"0.001"
            },
            "lot_size_filter":{
                "max_trading_qty":1000000,
                "min_trading_qty":1,
                "qty_step":1,
                "post_only_max_trading_qty":"5000000"
            }
        },
        {
            "name":"BTCUSDT",
            "alias":"BTCUSDT",
            "status":"Trading",
            "base_currency":"BTC",
            "quote_currency":"USDT",
            "price_scale":2,
            "taker_fee":"0.00075",
            "maker_fee":"-0.00025",
            "funding_interval":480,
            "leverage_filter":{
                "min_leverage":1,
                "max_leverage":100,
                "leverage_step":"0.01"
            },
            "price_filter":{
                "min_price":"0.5",
                "max_price":"999999.5",
                "tick_size":"0.5"
            },
            "lot_size_filter":{
                "max_trading_qty":100,
                "min_trading_qty":0.001,
                "qty_step":0.001,
                "post_only_max_trading_qty":"500"
            }
        },
        {
            "name":"BTCUSDM22",
            "alias":"BTCUSD0624",
            "status":"Trading",
            "base_currency":"BTC",
            "quote_currency":"USD",
            "price_scale":2,
            "taker_fee":"0.00075",
            "maker_fee":"-0.00025",
            "funding_interval":480,
            "leverage_filter":{
                "min_leverage":1,
                "max_leverage":100,
                "leverage_step":"0.01"
            },
            "price_filter":{
                "min_price":"0.5",
                "max_price":"999999.5",
                "tick_size":"0.5"
            },
            "lot_size_filter":{
                "max_trading_qty":1000000,
                "min_trading_qty":1,
                "qty_step":1,
                "post_only_max_trading_qty":"5000000"
            }
        }
    ],
    "time_now":"1615801223.589808"
}
```

t(:market_para_querySymbol)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpSymbols>/public/v1/symbols</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpSymbols"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|name |string |t(:row_response_comment_name)    |
|alias |string |t(:row_response_comment_name)    |
|t(:row_parameter_symbol_status) |string |t(:row_response_comment_status)    |
|base_currency |string |t(:row_response_comment_base_currency)    |
|quote_currency |string |t(:row_response_comment_quote_currency)    |
|price_scale |number |t(:row_response_comment_price_scale)    |
|taker_fee |string |t(:row_response_comment_taker_fee)    |
|maker_fee |string |t(:row_response_comment_maker_fee)    |
|funding_interval |number |t(:row_response_funding_interval)    |
|min_leverage |number |t(:row_response_comment_min_leverage)    |
|max_leverage |number |t(:row_response_comment_public_max_leverage)    |
|leverage_step |string |t(:row_response_comment_leverage_step)    |
|min_price |string |t(:row_response_comment_min_price)    |
|max_price |string |t(:row_response_comment_max_price)    |
|tick_size |string |t(:row_response_comment_tick_size)    |
|max_trading_qty |number |t(:row_response_comment_max_trading_qty)    |
|min_trading_qty |number |t(:row_response_comment_min_trading_qty)    |
|qty_step |number |t(:row_response_comment_qty_step)    |
|post_only_max_trading_qty |string |t(:row_response_comment_post_only_max_trading_qty)    |


### t(:markpricekline)
> t(:codequote_curlExample)

```console
curl "https://openapi-testnet.zoomex.com/public/v1/mark-price-kline/inverse?symbol=BTCUSD&interval=1&limit=2&from=1581231260"
```

```python
print(session_unauth.query_mark_price_kline(
    symbol="BTCUSD",
    interval="D",
    from_time=1653408000
))
```


> t(:codequote_responseExample)

```javascript

{
    "ret_code":0,
    "ret_msg":"OK",
    "ext_code":"",
    "ext_info":"",
    "result":[
        {
            "id":2,
            "symbol":"BTCUSD",
            "period":"1",
            "start_at":1582231260,
            "open":100,
            "high":120,
            "low":88,
            "close":115
        }
    ],
    "time_now":"1591263582.601795"
}
```

t(:linear_query_mark_price_kline)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=plmpk>/public/v1/mark-price-kline/inverse</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#plmpk"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |<b>true</b> |string |t(:row_comment_symbol) |
|<a href="#kline-interval-interval">interval</a> |<b>true</b> |string |t(:row_comment_interval) |
|from |<b>true</b> |integer |t(:row_comment_from_timestamp) |
|limit |false |integer |t(:linear_kline_row_comment_limit_200) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_symbol) |string |t(:row_comment_symbol) |
| period |string |t(:row_comment_period) |
| start_at |integer |t(:row_comment_startTime) |
| open |integer |t(:row_comment_open) |
| high |integer |t(:row_comment_high) |
| low |integer |t(:row_comment_low) |
| close |integer |t(:row_comment_close) |

### t(:queryindexpricekline)
> t(:codequote_curlExample)

```console
curl "https://openapi-testnet.zoomex.com/public/v1/index-price-kline/inverse?symbol=BTCUSD&interval=1&limit=2&from=1581231260"
```

```python
from pyzmx import inverse_perpetual
session_unauth = inverse_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com"
)
print(session_unauth.query_index_price_kline(
    symbol="BTCUSD",
    interval="D",
    from_time=1653408000
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code":0,
    "ret_msg":"OK",
    "ext_code":"",
    "ext_info":"",
    "result":[
        {
            "symbol":"BTCUSD",
            "period":"1",
            "open_time":1582231260,
            "open":"10106.09",
            "high":"10108.75",
            "low":"10104.66",
            "close":"10108.73"
        }
    ],
    "time_now":"1591263582.601795"
}
```
t(:inverse_query_index_price_kline)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=v2pIndexPriceKline>/public/v1/index-price-kline/inverse</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#v2pIndexPriceKline"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |<b>true</b> |string |t(:row_comment_symbol) |
|<a href="#kline-interval-interval">interval</a> |<b>true</b> |string |t(:row_comment_interval) |
|from |<b>true</b> |integer |t(:row_comment_from_timestamp) |
|limit |false |integer |t(:linear_kline_row_comment_limit_200) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| <a href="#symbol-symbol">symbol</a> |string |t(:row_comment_symbol) |
| period |string |t(:row_comment_period) |
| open_time |integer |t(:row_comment_startTime) |
| open |string |t(:row_comment_open) |
| high |string |t(:row_comment_high) |
| low |string |t(:row_comment_low) |
| close |string |t(:row_comment_close) |

