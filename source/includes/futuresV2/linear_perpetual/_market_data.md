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

### t(:instrument)
t(:instrument_remark)<br>
<br/>
<aside class="notice">
t(:instrument_covers)
</aside>

<aside class="warning">
t(:instrument_warn)
</aside>

> t(:codequote_curlExample)

```console
curl "https://openapi-testnet.zoomex.com/public/v2/market/instruments-info?category=linear&symbol=BTCUSDT"
```

```python
from pyzmx import usdt_perpetual
session_unauth = usdt_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com"
)
print(session_unauth.get_instruments_info(
    category="linear",
    symbol="BTCUSDT",
))
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "OK",
    "result": {
    "category": "linear",
      "list": [
      {
        "symbol": "BTCUSDT",
        "contractType": "LinearPerpetual",
        "status": "Trading",
        "baseCoin": "BTC",
        "quoteCoin": "USDT",
        "launchTime": "1585526400000",
        "priceScale": "2",
        "leverageFilter": {
          "minLeverage": "1",
          "maxLeverage": "100.00",
          "leverageStep": "0.01"
        },
        "priceFilter": {
          "minPrice": "0.50",
          "maxPrice": "999999.00",
          "tickSize": "0.50"
        },
        "lotSizeFilter": {
          "maxOrderQty": "100.000",
          "minOrderQty": "0.001",
          "qtyStep": "0.001",
          "postOnlyMaxOrderQty": "1000.000"
        },
        "fundingInterval": 480,
        "settleCoin": "USDT"
      }
    ],
      "nextPageCursor": ""
  },
  "retExtInfo": {},
  "time": 1672712495660
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=instrument>/public/v2/market/instruments-info</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#plIndexPriceKline"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
| Parameter                                 | Required | Type | Comments|
|:------------------------------------------|:-------|:-----|------ |
| <a href="#category-category">category</a> |<b>true</b> |string |t(:instrument_parameter_category)|
| <a href="#symbol-symbol">symbol</a>       |false |string |t(:instrument_parameter_symbol)|
| <a href="#status-status">status</a>       |false |string |t(:instrument_parameter_status)|
| baseCoin                                  |false |string |t(:instrument_parameter_baseCoin) |
| limit                                     |false |integer |t(:instrument_parameter_limit)|
| cursor                                    |false |string |t(:instrument_parameter_cursor)|

<p class="fake_header">t(:responseresponses)</p>
|t(:column_response)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| category | string | t(:instrument_response_category) |
| nextPageCursor | string | t(:instrument_response_nextPageCursor)|
|list|array| t(:instrument_response_list)|
|>symbol|string|t(:instrument_response_symbol)|
|>contractType| string| t(:instrument_response_contractType)|
|>status| string| t(:instrument_response_status)|
|>baseCoin| string| t(:instrument_response_baseCoin)|
|>quoteCoin| string| t(:instrument_response_quoteCoin)|
|>launchTime| string| t(:instrument_response_launchTime)|
|>priceScale| string| t(:instrument_response_priceScale)|
|>leverageFilter| Object| t(:instrument_response_leverageFilter)|
|>>minLeverage| string| t(:instrument_response_minLeverage)|
|>>maxLeverage| string| t(:instrument_response_maxLeverage)|
|>>leverageStep| string| t(:instrument_response_leverageStep)|
|>priceFilter| Object| t(:instrument_response_priceFilter)|
|>>minPrice| string| t(:instrument_response_minPrice)|
|>>maxPrice| string| t(:instrument_response_maxPrice)|
|>>tickSize| string| t(:instrument_response_tickSize)|
|>lotSizeFilter| Object| t(:instrument_response_lotSizeFilter)|
|>>maxOrderQty| string| t(:instrument_response_maxOrderQty)|
|>>minOrderQty| string| t(:instrument_response_minOrderQty)|
|>>qtyStep| string| t(:instrument_response_qtyStep)|
|>>postOnlyMaxOrderQty| string| t(:instrument_response_postOnlyMaxOrderQty)|
|>fundingInterval| integer| t(:instrument_response_fundingInterval)|
|>settleCoin| string| t(:instrument_response_settleCoin)
|><a href="#copytrading-copytrading">copyTrading</a>| string| t(:instrument_response_copyTrading)

### t(:tickers)
t(:tickers_remark)<br>
<br/>
<aside class="notice">
  t(:tickers_covers)
</aside>

> t(:codequote_curlExample)

```console
curl "https://openapi-testnet.zoomex.com/public/v2/market/tickers?category=inverse&symbol=BTCUSD"
```

```python
from pyzmx import usdt_perpetual
session_unauth = usdt_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com"
)
print(session_unauth.get_tickers(
    category="inverse",
    symbol="BTCUSD",
))
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "OK",
    "result": {
    "category": "inverse",
      "list": [
      {
        "symbol": "BTCUSD",
        "lastPrice": "16597.00",
        "indexPrice": "16598.54",
        "markPrice": "16596.00",
        "prevPrice24h": "16464.50",
        "price24hPcnt": "0.008047",
        "highPrice24h": "30912.50",
        "lowPrice24h": "15700.00",
        "prevPrice1h": "16595.50",
        "openInterest": "373504107",
        "openInterestValue": "22505.67",
        "turnover24h": "2352.94950046",
        "volume24h": "49337318",
        "fundingRate": "-0.001034",
        "nextFundingTime": "1672387200000",
        "ask1Size": "1",
        "bid1Price": "16596.00",
        "ask1Price": "16597.50",
        "bid1Size": "1"
      }
    ]
  },
  "retExtInfo": {},
  "time": 1672376496682
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=instrument>/public/v2/market/tickers</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#plIndexPriceKline"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
| Parameter                                 | Required | Type | Comments|
|:------------------------------------------|:-------|:-----|------ |
| <a href="#category-category">category</a> |<b>true</b> |string |t(:tickers_parameter_category)|
| <a href="#symbol-symbol">symbol</a>       |false |string |t(:tickers_parameter_symbol)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category | string | t(:tickers_response_category) |
|list|array| t(:tickers_response_list)|
|>symbol|string|t(:tickers_response_symbol)|
|>lastPrice| string| t(:tickers_response_lastPrice)|
|>indexPrice| string| t(:tickers_response_indexPrice)|
|>markPrice| string| t(:tickers_response_markPrice)|
|>prevPrice24h| string| t(:tickers_response_prevPrice24h)|
|>price24hPcnt| string| t(:tickers_response_price24hPcnt)|
|>highPrice24h| string| t(:tickers_response_highPrice24h)|
|>lowPrice24h| string| t(:tickers_response_lowPrice24h)|
|>prevPrice1h| string| t(:tickers_response_prevPrice1h)|
|>fundingRate| string| t(:tickers_response_fundingRate)|
|>nextFundingTime| string| t(:tickers_response_nextFundingTime)|
|>ask1Size| string| t(:tickers_response_ask1Size)|
|>bid1Price| Object| t(:tickers_response_bid1Price)|
|>ask1Price| string| t(:tickers_response_ask1Price)|
|>bid1Size| string| t(:tickers_response_bid1Size)|
