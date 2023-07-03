# t(:wallet)
t(:wallet_para)


### t(:balance)
> t(:codequote_curlExample)

```console
curl "https://openapi-testnet.zoomex.com/private/v1/asset/wallet/balance?api_key={api_key}&coin=BTC&timestamp={timestamp}&sign={sign}"
```

```python
from pyzmx import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.get_wallet_balance(coin="BTC"))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
        "BTC": {
            "equity": 1002,
            "available_balance": 999.99987471,
            "used_margin": 0.00012529,
            "order_margin": 0.00012529,
            "position_margin": 0,
            "occ_closing_fee": 0,
            "occ_funding_fee": 0,
            "wallet_balance": 1000,
            "realised_pnl": 0,
            "unrealised_pnl": 2,
            "cum_realised_pnl": 0,
            "given_cash": 0,
            "service_cash": 0
        }
    },
    "time_now": "1578284274.816029",
    "rate_limit_status": 98,
    "rate_limit_reset_ms": 1580885703683,
    "rate_limit": 100
}
```

t(:wallet_para_walletBalance)

<aside class="notice">
t(:wallet_aside_walletBalance)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpwBalance>/private/v1/asset/wallet/balance</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpwBalance"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:row_comment_coin_false) |



<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|equity |number |t(:row_comment_equity)  |
|available_balance |number |t(:row_comment_http_available_balance)  |
|used_margin |number |t(:row_comment_used_margin)    |
|order_margin|number |t(:row_comment_order_margin)    |
|position_margin |number |t(:row_comment_position_margin)  |
|occ_closing_fee |number |t(:row_comment_occ_closing_fee)  |
|occ_funding_fee |number |t(:row_comment_occ_funding_fee)  |
|wallet_balance |number |t(:row_comment_wallet_balance)  |
|realised_pnl |number |t(:row_comment_realised_pnl)  |
|unrealised_pnl |number |t(:row_comment_unrealised_pnl)  |
|cum_realised_pnl|number |t(:row_comment_cum_realised_pnl)  |
|given_cash |number |t(:row_response_comment_given_cash)  |
|service_cash |number |t(:row_response_comment_service_cash)  |

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
[//]: # (| baseCoin                                  |false |string |t(:tickers_parameter_baseCoin) |)
[//]: # (| expDate                                    |false |string |t(:tickers_parameter_expDate)|)

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
|>openInterest| Object| t(:tickers_response_openInterest)|
|>openInterestValue| string| t(:tickers_response_openInterestValue)|
|>turnover24h| string| t(:tickers_response_turnover24h)|
|>volume24h| string| t(:tickers_response_volume24h)|
|>fundingRate| string| t(:tickers_response_fundingRate)|
|>nextFundingTime| string| t(:tickers_response_nextFundingTime)|
[//]: # (|>predictedDeliveryPrice| Object| t(:tickers_response_predictedDeliveryPrice)|)
[//]: # (|>basisRate| string| t(:tickers_response_basisRate)|)
[//]: # (|>basis| string| t(:tickers_response_basis)|)
[//]: # (|>deliveryFeeRate| string| t(:tickers_response_deliveryFeeRate)|)
[//]: # (|>deliveryTime| string| t(:tickers_response_deliveryTime)|)
|>ask1Size| string| t(:tickers_response_ask1Size)|
|>bid1Price| Object| t(:tickers_response_bid1Price)|
|>ask1Price| string| t(:tickers_response_ask1Price)|
|>bid1Size| string| t(:tickers_response_bid1Size)|

