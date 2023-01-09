# t(:marketdata)
t(:market_para_auth)

### t(:orderbook)
<a href="/docs/futuresV2/inverse#t-orderbook">t(:shared_endpoint_desc)</a>

### t(:querykline)
> t(:codequote_curlExample)

```console
curl https://openapi-testnet.zoomex.com/public/v1/kline/usdt?symbol=BTCUSDT&interval=1&limit=2&from=1581231260
```

```python
from pyzmx import usdt_perpetual
session_unauth = usdt_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com"
)
print(session_unauth.query_kline(
    symbol="BTCUSDT",
    interval=1,
    limit=2,
    from_time=1581231260
))
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
	    "id": 3866948,
        "symbol": "BTCUSDT",
        "period": "1",
        "start_at": 1577836800,
        "volume": 1451.59,
        "open": 7700,
        "high": 999999,
        "low": 0.5,
        "close": 6000,
        "interval": "1",
        "open_time": 1577836800,
        "turnover": 2.4343353100000003,
	}],
	"time_now": "1581928016.558522"
}
```

t(:linear_market_para_querykline)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpSymbols>/public/v1/kline/usdt</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpSymbols"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|<a href="#kline-interval-interval">interval</a> |<b>true</b> |string |t(:row_comment_interval) |
|from |<b>true</b> |integer |t(:row_comment_from_timestamp) |
|limit |false |integer |t(:linear_kline_row_comment_limit_200) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_symbol)  |string |t(:row_comment_symbol) |
| period |string |t(:row_comment_period) |
| interval |string |t(:row_comment_period) |
| start_at |integer |t(:row_comment_startTime) |
| open_time |integer |t(:row_comment_resp_open_time) |
| volume |number |t(:row_comment_resp_volume) |
| open |integer |t(:row_comment_open) |
| high |integer |t(:row_comment_high) |
| low |number |t(:row_comment_low) |
| close |integer |t(:row_comment_close) |
| turnover |number |t(:row_comment_resp_turnover) |

### t(:fundingrate)
> t(:codequote_curlExample)

```console
curl https://openapi-testnet.zoomex.com/public/v1/funding/prev-funding-rate/usdt?symbol=BTCUSDT
```

```python
from pyzmx import usdt_perpetual
session_unauth = usdt_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com"
)
print(session_unauth.get_the_last_funding_rate(
    symbol="BTCUSDT"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code":0,
    "ret_msg":"OK",
    "ext_code":"",
    "ext_info":"",
    "result":{
        "symbol":"BTCUSDT",
        "funding_rate":-0.00005965,
        "funding_rate_timestamp":"2020-04-07T08:00:00.000Z"
    },
    "time_now":"1586251109.454281"
}
```

t(:market_para_fundingRate)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpPreFundingRate>/public/v1/funding/prev-funding-rate/usdt</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpPreFundingRate"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|funding_rate |number |t(:row_comment_funding_rate)  |
|funding_rate_timestamp |string |t(:row_comment_funding_rate_timestamp)  |











### t(:markpricekline)
> t(:codequote_curlExample)

```console
curl https://openapi-testnet.zoomex.com/public/v1/mark-price-kline/usdt?symbol=BTCUSDT&interval=1&limit=2&from=1581231260
```

```python
from pyzmx import usdt_perpetual
session_unauth = usdt_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com"
)
print(session_unauth.query_mark_price_kline(
    symbol="BTCUSDT",
    interval=1,
    limit=2,
    from_time=1581231260
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
	    "id": 3866948,
        "symbol": "BTCUSDT",
        "period": "1",
        "start_at": 1577836800,
        "open": 7700,
        "high": 999999,
        "low": 0.5,
        "close": 6000
	},
	{
	    "id": 3866948,
        "symbol": "BTCUSDT",
        "period": "1",
        "start_at": 1577836800,
        "open": 7700,
        "high": 999999,
        "low": 0.5,
        "close": 6000
	}],
	"time_now": "1581928016.558522"
}
```

t(:linear_query_mark_price_kline)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=plmpk>/public/v1/mark-price-kline/usdt</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#plmpk"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
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
| low |number |t(:row_comment_low) |
| close |integer |t(:row_comment_close) |


### t(:queryindexpricekline)
> t(:codequote_curlExample)

```console
curl "https://openapi-testnet.zoomex.com/public/v1/index-price-kline/usdt?symbol=BTCUSDT&interval=1&limit=2&from=1581231260"
```

```python
from pyzmx import usdt_perpetual
session_unauth = usdt_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com"
)
print(session_unauth.query_index_price_kline(
    symbol="BTCUSDT",
    interval=1,
    limit=2,
    from_time=1581231260
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code":0,
    "ret_msg":"OK",
    "ext_code":"",
    "ext_info":"",
    "result":[{
        "symbol":"BTCUSDT",
        "period":"1",
        "open_time":1582231260,
        "open":"10106.09",
        "high":"10108.75",
        "low":"10104.66",
        "close":"10108.73"
    }],
    "time_now":"1591263582.601795"
}
```
t(:inverse_query_index_price_kline)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=plIndexPriceKline>/public/v1/index-price-kline/usdt</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#plIndexPriceKline"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

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


