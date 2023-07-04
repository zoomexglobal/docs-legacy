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

