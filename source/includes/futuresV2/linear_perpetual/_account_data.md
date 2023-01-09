# t(:accountdata)
t(:account_para)

## t(:activeorders)
### t(:placeactive)
> t(:codequote_curlExample)

```console
curl https://openapi-testnet.zoomex.com/private/v1/order/create/usdt \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","side":"Buy","symbol":"BTCUSD","order_type":"Market","qty":10,"time_in_force":"GoodTillCancel","timestamp":{timestamp},"sign":"{sign}"}'
```

```python
from pyzmx import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.place_active_order(
    symbol="BTCUSDT",
    side="Sell",
    order_type="Limit",
    qty=0.01,
    price=8083,
    time_in_force="GoodTillCancel",
    reduce_only=False,
    close_on_trigger=False
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
        "order_id": "a6c64aa0-c80b-4865-ae35-99be5fab3535",
        "user_id": 533285,
        "symbol": "MANAUSDT",
        "side": "Sell",
        "order_type": "Limit",
        "price": 0.8,
        "qty": 100,
        "time_in_force": "GoodTillCancel",
        "order_status": "Created",
        "last_exec_price": 0,
        "cum_exec_qty": 0,
        "cum_exec_value": 0,
        "cum_exec_fee": 0,
        "reduce_only": false,
        "close_on_trigger": false,
        "order_link_id": "Mactive001",
        "created_time": "2022-06-22T01:46:11Z",
        "updated_time": "2022-06-22T01:46:11Z",
        "take_profit": 0.65,
        "stop_loss": 0.99,
        "tp_trigger_by": "MarkPrice",
        "sl_trigger_by": "LastPrice",
        "position_idx": 2
    },
    "time_now": "1655862371.660491",
    "rate_limit_status": 99,
    "rate_limit_reset_ms": 1655862371657,
    "rate_limit": 100
}
```

t(:linear_account_para_placeActive)

<aside class="warning">
t(:account_aside_placeActive_linear_warn)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/private/v1/order/create/usdt</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_side) |<b>true</b> |string |t(:row_comment_side)    |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)   |
|t(:row_parameter_order_type) |<b>true</b> |string |t(:row_comment_activeOrderType)   |
|t(:row_parameter_quantity) |<b>true</b> |number |t(:linear_row_comment_qty) |
|t(:row_parameter_price) |false |number |t(:row_comment_price) |
|t(:row_parameter_time_in_force) |<b>true</b> |string |t(:row_comment_timeInForce) |
|reduce_only |<b>true</b> |bool |t(:linear_row_comment_reduceOnly) |
|close_on_trigger |<b>true</b> |bool |t(:linear_row_comment_closeOnTrigger)
|order_link_id |false |string |t(:row_comment_orderLinkId) |
|take_profit |false |number |t(:row_comment_takeProfit) |
|stop_loss |false |number |t(:row_comment_stopLoss) |
|t(:row_parameter_tp_trigger_by) |false |string |t(:account_row_comment_tp_trigger_by) |
|t(:row_parameter_sl_trigger_by) |false |string |t(:account_row_comment_sl_trigger_by) |
|position_idx |false |integer |t(:row_comment_position_idx_create_order)  |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| order_id |string |t(:row_comment_order_id) |
| user_id |number |t(:row_comment_userID) |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_order_type) |string |t(:row_comment_order_type)  |
|t(:row_parameter_price) |number |t(:row_comment_resp_price)  |
|qty |number |t(:row_response_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|last_exec_price |number |t(:row_comment_last_exec_price)  |
|cum_exec_qty |number |t(:linear_resp_field_cum_exec_qty)  |
|cum_exec_value |number |t(:linear_resp_field_cum_exec_value)  |
|cum_exec_fee |number |t(:linear_resp_field_cum_exec_fee)  |
|reduce_only |bool |t(:linear_resp_field_reduce_only)  |
|close_on_trigger |bool |t(:row_response_close_on_trigger)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|created_time |string |t(:row_comment_created_at)  |
|updated_time |string |t(:row_comment_updated_at)  |
|take_profit |number |t(:row_comment_take_profit)  |
|stop_loss |number |t(:row_comment_stop_loss)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by)  |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by)  |
|position_idx |integer |t(:row_comment_position_idx)  |

### t(:getactive)
> t(:codequote_curlExample)

```console
curl "https://openapi-testnet.zoomex.com/private/v1/order/list/usdt?api_key={api_key}&timestamp={timestamp}&sign={sign}&symbol=BTCUSDT"
```

```python
from pyzmx import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.get_active_order(
    symbol="BTCUSDT"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
        "current_page": 1,
        "data": [
            {
                "order_id": "a6c64aa0-c80b-4865-ae35-99be5fab3535",
                "user_id": 533285,
                "symbol": "MANAUSDT",
                "side": "Sell",
                "order_type": "Limit",
                "price": 0.8,
                "qty": 100,
                "time_in_force": "GoodTillCancel",
                "order_status": "Filled",
                "last_exec_price": 0.8315,
                "cum_exec_qty": 100,
                "cum_exec_value": 83.15,
                "cum_exec_fee": 0.04989,
                "reduce_only": false,
                "close_on_trigger": false,
                "order_link_id": "Mactive001",
                "created_time": "2022-06-22T01:46:11Z",
                "updated_time": "2022-06-22T01:46:11Z",
                "take_profit": 0.65,
                "stop_loss": 0.99,
                "tp_trigger_by": "MarkPrice",
                "sl_trigger_by": "LastPrice"
            }
        ]
    },
    "time_now": "1655862613.007213",
    "rate_limit_status": 598,
    "rate_limit_reset_ms": 1655862613003,
    "rate_limit": 600
}
```

t(:account_para_getActive)

<aside class="warning">
t(:getOrderList_warning)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oaoList>/private/v1/order/list/usdt</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaoList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|order_id |false |string |t(:account_row_comment_orderId) |
|order_link_id |false |string |t(:row_comment_orderLinkId) |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|t(:row_parameter_order) |false |string |t(:row_comment_order)  |
|page |false |integer |t(:row_comment_page_max50) |
|limit |false |integer |t(:row_comment_limit) |
|t(:row_parameter_order_status) |false |string |t(:linear_account_row_comment_orderStatus) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|order_id |string |t(:account_row_comment_orderId) |
| user_id |number |t(:row_comment_userID) |
| t(:row_parameter_symbol) |string |t(:row_comment_symbol) |
| t(:row_parameter_side) |string |t(:row_comment_side) |
| t(:row_parameter_order_type) |string |t(:row_comment_order_type) |
| price  |number |t(:row_comment_resp_price) |
| qty  |number |t(:linear_row_comment_qty) |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|last_exec_price |number |t(:row_comment_last_exec_price)  |
|cum_exec_qty |number |t(:linear_resp_field_cum_exec_qty)  |
|cum_exec_value |number |t(:linear_resp_field_cum_exec_value)  |
|cum_exec_fee |number |t(:linear_resp_field_cum_exec_fee)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|reduce_only |bool |t(:linear_resp_field_reduce_only)  |
|close_on_trigger |bool |t(:row_response_close_on_trigger)  |
|created_time |string |t(:row_comment_created_at)  |
|updated_time |string |t(:row_comment_updated_at)  |
|take_profit |number |t(:row_comment_take_profit)  |
|stop_loss |number |t(:row_comment_stop_loss)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by) |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by) |

### t(:cancelactive)
> t(:codequote_curlExample)

```console
curl https://openapi-testnet.zoomex.com/private/v1/order/cancel/usdt \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","order_id":"","timestamp":{timestamp},"sign":"{sign}"}'
```

```python
from pyzmx import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.cancel_active_order(
    symbol="BTCUSDT",
    order_id=""
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
        "order_id":"bd1844f-f3c0-4e10-8c25-10fea03763f6",
    },
    "time_now": "1575112681.814760",
    "rate_limit_status": 98,
    "rate_limit_reset_ms": 1580885703683,
    "rate_limit": 100
}
```

t(:account_para_cancelActive)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCancel>/private/v1/order/cancel/usdt</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancel"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|order_id |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|order_link_id |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|order_id |string |t(:account_row_comment_orderId) |



### t(:replaceactive)
> t(:codequote_curlExample)

```console
curl https://openapi-testnet.zoomex.com/private/v1/order/replace/usdt \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","order_id":"","p_r_qty":2,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python
from pyzmx import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.replace_active_order(
    symbol="BTCUSDT",
    order_id="",
    p_r_qty=2
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": {
        "order_id": "efa44157-c355-4a98-b6d6-1d846a936b93"
    },
    "time_now": "1539778407.210858",
    "rate_limit_status": 99,
    "rate_limit_reset_ms": 1580885703683,
    "rate_limit": 100             
}
```

t(:account_para_replaceActive)

<aside class="notice">
t(:account_aside_replaceActive)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=oaoReplace>/private/v1/order/replace/usdt</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaoReplace"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|order_id |false |string |t(:row_comment_order_id_replace) |
|order_link_id |false |string |t(:row_comment_order_link_id_replace) |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|p_r_qty |false |number |t(:row_comment_pRQty) |
|p_r_price |false |number |t(:row_comment_pRPrice) |
|take_profit |false |number |t(:row_comemnt_replace_take_profit)  |
|stop_loss |false |number |t(:row_comemnt_replace_stop_loss)  |
|t(:row_parameter_tp_trigger_by) |false |string |t(:account_row_comment_tp_trigger_by) |
|t(:row_parameter_sl_trigger_by) |false |string |t(:account_row_comment_sl_trigger_by) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|order_id |string |t(:account_row_comment_orderId) |


## t(:position)
### t(:myposition)
> t(:codequote_curlExample)

```console
curl https://openapi-testnet.zoomex.com/private/v1/position/list/usdt?api_key={api_key}&symbol=BTCUSDT&timestamp={timestamp}&sign={sign}"
```

```python
session_auth = usdt_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com",
    api_key="XXXXXXXXXXXX",
    api_secret="XXXXXXXXXXXXXXXXXXXXXX"
)
print(session_auth.my_position(
    symbol="BTCUSDT"
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
            "user_id": 533285,
            "symbol": "XRPUSDT",
            "side": "Buy",
            "size": 0,
            "position_value": 0,
            "entry_price": 0,
            "liq_price": 0,
            "bust_price": 0,
            "leverage": 5,
            "auto_add_margin": 0,
            "is_isolated": true,
            "position_margin": 0,
            "occ_closing_fee": 0,
            "realised_pnl": 0,
            "cum_realised_pnl": -16.35115218,
            "free_qty": 0,
            "tp_sl_mode": "Full",
            "unrealised_pnl": 0,
            "deleverage_indicator": 0,
            "risk_id": 41,
            "stop_loss": 0,
            "take_profit": 0,
            "trailing_stop": 0,
            "position_idx": 1,
            "mode": "BothSide"
        },
        {
            "user_id": 533285,
            "symbol": "XRPUSDT",
            "side": "Sell",
            "size": 50,
            "position_value": 19.58,
            "entry_price": 0.3916,
            "liq_price": 0.4529,
            "bust_price": 0.4568,
            "leverage": 6,
            "auto_add_margin": 0,
            "is_isolated": true,
            "position_margin": 3.2633354,
            "occ_closing_fee": 0.013704,
            "realised_pnl": 0,
            "cum_realised_pnl": 0.90620182,
            "free_qty": 50,
            "tp_sl_mode": "Full",
            "unrealised_pnl": 3.395,
            "deleverage_indicator": 2,
            "risk_id": 41,
            "stop_loss": 0.5,
            "take_profit": 0.28,
            "trailing_stop": 0,
            "tp_trigger_by": 1,
            "sl_trigger_by": 1,
            "position_idx": 2,
            "mode": "BothSide"
        }
    ],
    "time_now": "1655868796.293226",
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1655868796290,
    "rate_limit": 120
}

//t(:resp_field_position_list)
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": [
        {
            "data": {
                "user_id": 533285,
                "symbol": "10000NFTUSDT",
                "side": "Sell",
                "size": 0,
                "position_value": 0,
                "entry_price": 0,
                "liq_price": 0,
                "bust_price": 0,
                "leverage": 10,
                "auto_add_margin": 0,
                "is_isolated": false,
                "position_margin": 0,
                "occ_closing_fee": 0,
                "realised_pnl": 0,
                "cum_realised_pnl": 0,
                "free_qty": 0,
                "tp_sl_mode": "Full",
                "unrealised_pnl": 0,
                "deleverage_indicator": 0,
                "risk_id": 1,
                "stop_loss": 0,
                "take_profit": 0,
                "trailing_stop": 0,
                "position_idx": 2,
                "mode": "BothSide"
            },
            "is_valid": true
        },
        ...
        {
            "data": {
                "user_id": 533285,
                "symbol": "10000NFTUSDT",
                "side": "Buy",
                "size": 0,
                "position_value": 0,
                "entry_price": 0,
                "liq_price": 0,
                "bust_price": 0,
                "leverage": 10,
                "auto_add_margin": 0,
                "is_isolated": false,
                "position_margin": 0,
                "occ_closing_fee": 0,
                "realised_pnl": 0,
                "cum_realised_pnl": 0,
                "free_qty": 0,
                "tp_sl_mode": "Full",
                "unrealised_pnl": 0,
                "deleverage_indicator": 0,
                "risk_id": 1,
                "stop_loss": 0,
                "take_profit": 0,
                "trailing_stop": 0,
                "position_idx": 1,
                "mode": "BothSide"
            },
            "is_valid": true
        }
    ],
    "time_now": "1604302080.356538",
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1604302080353,
    "rate_limit": 120
}
```

t(:account_para_myPosition)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=pList>/private/v1/position/list/usdt</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |false |string |t(:row_comment_symbol)    |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|size |number |t(:row_comment_position_size)  |
|position_value |number |t(:row_comment_position_value)  |
|entry_price |number |t(:linear_resp_field_entry_price)  |
|liq_price |number |t(:linear_resp_field_liq_price)  |
|bust_price |number |t(:linear_resp_field_bust_price)  |
|leverage |number |t(:resp_field_leverage)  |
|auto_add_margin |number |t(:row_comment_auto_add_margin)  |
|is_isolated | bool | t(:row_comment_isolated) |
|position_margin |number |t(:linear_resp_field_position_margin)  |
|occ_closing_fee |number |t(:linear_resp_field_occ_closing_fee)  |
|realised_pnl |number |t(:linear_resp_field_realised_pnl)  |
|cum_realised_pnl |number |t(:linear_resp_field_cum_realised_pnl)  |
|free_qty |number |t(:linear_resp_field_free_qty)  |
|t(:row_parameter_tp_sl_mode) |string |t(:linear_resp_tp_sl_mode)  |
|deleverage_indicator |number |t(:row_comment_deleverage_indicator)  |
|unrealised_pnl |number |t(:row_comment_unrealised_pnl)  |
|risk_id  |integer |t(:row_comment_riskId) |
|take_profit |number |t(:row_comment_take_profit)  |
|stop_loss |number |t(:row_comment_stop_loss)  |
|trailing_stop |number |t(:row_comment_trailing_stop)  |
|position_idx |integer |t(:row_comment_position_idx)  |
|mode |string |t(:linear_comment_positionmode) |


### t(:switchmode)

```python
from pyzmx import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com",
    api_key="XXXXXXXXXXXX",
    api_secret="XXXXXXXXXXXXXXXXXXXXXX"
)
print(session_auth.full_partial_position_tp_sl_switch(
    symbol="BTCUSDT",
    tp_sl_mode="Partial"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
        "tp_sl_mode": "Partial"
    },
    "time_now": "1598266294.610276",
    "rate_limit_status": 72,
    "rate_limit_reset_ms": 1598266294607,
    "rate_limit": 75
}
```

t(:linear_private_switchmode)

<aside class="notice">
t(:switchmode_aside)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pltcList>/private/v1/tpsl/switch-mode/usdt</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pltcList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|t(:row_parameter_tp_sl_mode) |<b>true</b> |string |t(:linear_resp_tp_sl_mode)  |



<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_tp_sl_mode) |string |t(:linear_resp_tp_sl_mode)  |


### t(:tradingstop)
> t(:codequote_curlExample)

```console
curl https://openapi-testnet.zoomex.com/private/v1/position/trading-stop/usdt \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","side":"Buy","take_profit":10,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python
from pyzmx import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com",
    api_key="XXXXXXXXXXXX",
    api_secret="XXXXXXXXXXXXXXXXXXXXXX"
)
print(session_auth.set_trading_stop(
    symbol="BTCUSDT",
    side="Buy",
    take_profit=10
))
```

> t(:codequote_responseExample)

```javascript
{
  "ret_code": 0,
  "ret_msg": "OK",
  "ext_code": "",
  "ext_info": "",
  "result": null,
  "time_now": "1586780408.193508",
  "rate_limit_status": 73,
  "rate_limit_reset_ms": 1586780408191,
  "rate_limit": 75
}
```

t(:account_para_tradingStop_linear)

<aside class="notice">
t(:account_aside_tradingStop)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pSetTpSlTs>/private/v1/position/trading-stop/usdt</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pSetTpSlTs"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|t(:row_parameter_side) |<b>true</b> |string |t(:account_row_comment_side)    |
|take_profit |false |number |t(:account_row_comment_takeProfit) |
|stop_loss |false |number |t(:account_row_comment_stopLoss) |
|trailing_stop |false |number |t(:account_row_comment_trailingStop) |
|t(:row_parameter_tp_trigger_by) | false | string | t(:account_row_comment_tp_trigger_by)
|t(:row_parameter_sl_trigger_by) | false | string | t(:account_row_comment_sl_trigger_by)
|sl_size |false |number |t(:row_comment_sl_size) |
|tp_size |false |number |t(:row_comment_tp_size) |
|position_idx |false |integer |t(:row_comment_position_idx)  |


### t(:addmargin)
> t(:codequote_curlExample)

```console
curl https://openapi-testnet.zoomex.com \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","side":"Buy","margin":0.01","timestamp":{timestamp},"sign":"{sign}"}'
```
```python
from pyzmx import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com",
    api_key="XXXXXXXXXXXX",
    api_secret="XXXXXXXXXXXXXXXXXXXXXX"
)
print(session_auth.add_reduce_margin(
    symbol="BTCUSDT",
    side="Buy",
    margin=0.01
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
        "PositionListResult": {
            "user_id": 533285,
            "symbol": "XRPUSDT",
            "side": "Sell",
            "size": 50,
            "position_value": 19.58,
            "entry_price": 0.3916,
            "liq_price": 0.5267,
            "bust_price": 0.5307,
            "leverage": 10,
            "auto_add_margin": 0,
            "is_isolated": true,
            "position_margin": 6.9550018,
            "occ_closing_fee": 0.015921,
            "realised_pnl": 0,
            "cum_realised_pnl": 0.90620182,
            "free_qty": 50,
            "tp_sl_mode": "Full",
            "unrealised_pnl": 3.475,
            "deleverage_indicator": 2,
            "risk_id": 41,
            "stop_loss": 0.5,
            "take_profit": 0.28,
            "trailing_stop": 0,
            "tp_trigger_by": 1,
            "sl_trigger_by": 1,
            "position_idx": 2,
            "mode": "BothSide"
        },
        "wallet_balance": 2108.58165689,
        "available_balance": 2091.03640109
    },
    "time_now": "1655870135.180074",
    "rate_limit_status": 73,
    "rate_limit_reset_ms": 1655870135178,
    "rate_limit": 75
}
```

t(:linear_account_para_addMargin)


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pAddMargin>/private/v1/position/add-margin/usdt</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pAddMargin"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|t(:row_parameter_side) |<b>true</b> |string |t(:row_comment_side)    |
|margin |<b>true</b> |number |t(:linear_account_row_comment_margin) |
|position_idx |false |integer |t(:row_comment_position_idx)  |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|size |number |t(:row_comment_position_size)  |
|position_value |number |t(:linear_resp_field_position_value)  |
|entry_price |number |t(:linear_resp_field_entry_price)  |
|liq_price |number |t(:linear_resp_field_liq_price)  |
|bust_price |number |t(:linear_resp_field_bust_price)  |
|leverage |number |t(:resp_field_leverage)  |
|auto_add_margin |number |t(:row_comment_auto_add_margin)  |
|is_isolated |bool |t(:isIsolated)  |
|position_margin |number |t(:linear_resp_field_position_margin)  |
|occ_closing_fee |number |t(:linear_resp_field_occ_closing_fee)  |
|realised_pnl |number |t(:linear_resp_field_realised_pnl)  |
|cum_realised_pnl |number |t(:linear_resp_field_cum_realised_pnl)  |
|free_qty |number |t(:linear_resp_field_free_qty)  |
|t(:row_parameter_tp_sl_mode) |string |t(:linear_resp_tp_sl_mode)  |
|unrealised_pnl |number |t(:row_comment_unrealised_pnl)  |
|deleverage_indicator |number |t(:row_comment_deleverage_indicator)  |
|risk_id |number |t(:row_comment_riskId)  |
|stop_loss |number |t(:row_comment_stop_loss)  |
|take_profit |number |t(:row_comment_take_profit)  |
|trailing_stop |number |t(:row_comment_trailing_stop)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by)  |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by)  |
|position_idx |integer |t(:row_comment_position_idx)  |
|mode |string |t(:linear_comment_positionmode) |
|wallet_balance |number |t(:row_comment_wallet_balance)  |
|available_balance |number |t(:row_comment_available_balance)  |


### t(:setleverage)
> t(:codequote_curlExample)

```console
curl https://openapi-testnet.zoomex.com/private/v1/position/set-leverage/usdt \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","buy_leverage":10,"sell_leverage":10"sign":"{sign}"}'
```

```python
from pyzmx import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com",
    api_key="XXXXXXXXXXXX",
    api_secret="XXXXXXXXXXXXXXXXXXXXXX"
)
print(session_auth.set_leverage(
    symbol="BTCUSDT",
    buy_leverage=10,
    sell_leverage=10
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": null,
    "time_now": "1585881527.650138",
    "rate_limit_status": 74,
    "rate_limit_reset_ms": 1585881527648,
    "rate_limit": 75
}
```

t(:linear_account_para_setLeverage)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pSetLeverage>/private/v1/position/set-leverage/usdt</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pSetLeverage"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|buy_leverage |<b>true</b> |number |t(:linear_row_comment_leverage)  |
|sell_leverage |<b>true</b> |number |t(:linear_row_comment_leverage)  |

## t(:risklimit)
### t(:getrisklimit)
> t(:codequote_curlExample)

```console
curl "https://openapi-testnet.zoomex.com/public/v1/risk-limit/usdt?symbol=BTCUSDT"
```


```python
from pyzmx import usdt_perpetual
session_unauth = usdt_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com"
)
print(session_unauth.get_risk_limit(
    symbol="BTCUSDT"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "result": [
        {
            "id": 11,
            "symbol": "ETHUSDT",
            "limit": 900000,
            "maintain_margin": 0.005,
            "starting_margin": 0.01,
            "section": [
                "1",
                "3",
                "5",
                "10",
                "25",
                "50",
                "80"
            ],
            "is_lowest_risk": 1,
            "created_at": "",
            "updated_at": "",
            "max_leverage": 100
        },
        ...
        {
            "id": 36,
            "symbol": "ETHUSDT",
            "limit": 50000000,
            "maintain_margin": 0.13,
            "starting_margin": 0.2,
            "section": [
                "1",
                "2",
                "3",
                "4"
            ],
            "is_lowest_risk": 0,
            "created_at": "",
            "updated_at": "",
            "max_leverage": 5
        }
    ],
    "ext_code": "",
    "ext_info": "",
    "time_now": "1662629653.373425"
}
```

t(:account_para_getRisk)

<aside class="notice">
t(:account_aside_getRisk_linear)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oawrlList>/public/v1/risk-limit/usdt</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawrlList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id |number |t(:row_comment_riskId)  |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)  |
|limit |number |t(:row_comment_risk_limit)    |
|maintain_margin |number |t(:row_comment_maintain_margin)  |
|starting_margin |number |t(:row_comment_starting_margin_linear)  |
|section |string |t(:row_comment_section)  |
|is_lowest_risk |number |t(:row_comment_is_lowest_risk)    |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|max_leverage |string |t(:row_comment_max_leverage)  |

### t(:setrisklimit)

> t(:codequote_curlExample)

```console
curl https://openapi-testnet.zoomex.com/private/v1/position/set-risk/usdt \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","risk_id":2,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python
from pyzmx import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com",
    api_key="XXXXXXXXXXXX",
    api_secret="XXXXXXXXXXXXXXXXXXXXXX"
)
print(session_auth.set_risk_limit(
    symbol="BTCUSDT",
    side="Buy",
    risk_id=1
))
```

> t(:codequote_responseExample)

```javascript  
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
        "risk_id": 2
    },
    "time_now": "1609839125.563609",
    "rate_limit_status": 73,
    "rate_limit_reset_ms": 1609839125560,
    "rate_limit": 75
}
```
t(:account_para_setRisk)

<aside class="notice">
t(:account_aside_getRisk_linear)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=plpSetRisk>/private/v1/position/set-risk/usdt</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#plpSetRisk"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|t(:row_parameter_side) |<b>true</b> |string |t(:row_comment_side)    |
|risk_id |<b>true</b> |integer |t(:row_comment_riskId) |
|position_idx |false |integer |t(:row_comment_position_idx)  |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|risk_id |number |t(:row_comment_riskId)  |
