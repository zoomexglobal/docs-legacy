# t(:accountdata)
t(:account_para)

## t(:activeorders)
### t(:placeactive)
> t(:codequote_curlExample)

```console
curl https://openapi-testnet.zoomex.com/private/v1/order/create/inverse \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","side":"Buy","symbol":"BTCUSD","order_type":"Market","qty":10,"time_in_force":"GoodTillCancel","timestamp":{timestamp},"sign":"{sign}"}'

```

```python
from pyzmx import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.place_active_order(
    symbol="BTCUSD",
    side="Buy",
    order_type="Market",
    qty=1,
    time_in_force="GoodTillCancel"
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
        "user_id": 533285,
        "order_id": "a1904030-f99c-4e35-9217-111591f08493",
        "symbol": "BTCUSD",
        "side": "Buy",
        "order_type": "Limit",
        "price": 20010,
        "qty": 200,
        "time_in_force": "GoodTillCancel",
        "order_status": "Created",
        "last_exec_time": 0,
        "last_exec_price": 0,
        "leaves_qty": 200,
        "cum_exec_qty": 0,
        "cum_exec_value": 0,
        "cum_exec_fee": 0,
        "reject_reason": "EC_NoError",
        "order_link_id": "",
        "created_at": "2022-06-20T06:56:22.070Z",
        "updated_at": "2022-06-20T06:56:22.070Z",
        "take_profit": "22000.00",
        "stop_loss": "19000.00",
        "tp_trigger_by": "MarkPrice",
        "sl_trigger_by": "MarkPrice"
    },
    "time_now": "1655708182.071362",
    "rate_limit_status": 99,
    "rate_limit_reset_ms": 1655708182068,
    "rate_limit": 100
}
```

t(:account_para_placeActive)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/private/v1/order/create/inverse</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_side) |<b>true</b> |string |t(:row_comment_side)    |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)   |
|t(:row_parameter_order_type) |<b>true</b> |string |t(:row_comment_activeOrderType)   |
|t(:row_parameter_quantity) |<b>true</b> |integer |t(:row_comment_qty) |
|t(:row_parameter_price) |false |number |t(:row_comment_resp_price) |
|t(:row_parameter_time_in_force) |<b>true</b> |string |t(:row_comment_timeInForce) |
|reduce_only |false |bool |t(:row_comment_reduceOnly) |
|close_on_trigger |false |bool |t(:row_comment_closeOnTrigger)
|order_link_id |false |string |t(:row_comment_orderLinkId) |
|take_profit |false |number |t(:row_comment_takeProfit) |
|stop_loss |false |number |t(:row_comment_stopLoss) |
|t(:row_parameter_tp_trigger_by) |false |string |t(:account_row_comment_tp_trigger_by) |
|t(:row_parameter_sl_trigger_by) |false |string |t(:account_row_comment_sl_trigger_by) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| user_id |number |t(:row_comment_userID) |
| order_id |string |t(:row_comment_order_id) |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_order_type) |string |t(:row_comment_order_type)  |
|t(:row_parameter_price) |number |t(:row_comment_resp_price)  |
|qty |number |t(:row_response_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|last_exec_time |string |t(:row_comment_last_exec_time)  |
|last_exec_price |string |t(:row_comment_last_exec_price)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|cum_exec_qty |number |t(:linear_resp_field_cum_exec_qty)  |
|cum_exec_value |number |t(:linear_resp_field_cum_exec_value)  |
|cum_exec_fee |number |t(:linear_resp_field_cum_exec_fee)  |
|reject_reason |string |t(:row_comment_reject_reason)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|take_profit |string |t(:row_comment_take_profit)  |
|stop_loss |string |t(:row_comment_stop_loss)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by)  |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by)  |

### t(:getactive)
> t(:codequote_curlExample)

```console
curl "https://openapi-testnet.zoomex.com/private/v1/order/list/inverse?api_key={api_key}&timestamp={timestamp}&sign={sign}&symbol=BTCUSD"
```

```python
from pyzmx import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.get_active_order(
    symbol="BTCUSD",
    order_status="New"
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
        "data": [
            {
                "user_id": 533285,
                "position_idx": 0,
                "order_status": "New",
                "symbol": "BTCUSD",
                "side": "Buy",
                "order_type": "Limit",
                "price": "20010",
                "qty": "200",
                "time_in_force": "GoodTillCancel",
                "order_link_id": "",
                "order_id": "a1904030-f99c-4e35-9217-111591f08493",
                "created_at": "2022-06-20T06:56:22.070Z",
                "updated_at": "2022-06-20T06:56:22.075Z",
                "leaves_qty": "200",
                "leaves_value": "0.009995",
                "cum_exec_qty": "0",
                "cum_exec_value": "0",
                "cum_exec_fee": "0",
                "reject_reason": "EC_NoError",
                "take_profit": "22000.0000",
                "stop_loss": "19000.0000",
                "tp_trigger_by": "MarkPrice",
                "sl_trigger_by": "MarkPrice"
            }
        ],
        "cursor": "/oIljKFOerbXfuWAmnc33qCc1649q+xLuuagMYyoYh6pV+BShVJ8ph439Xw8ywSp"
    },
    "time_now": "1655708401.042813",
    "rate_limit_status": 599,
    "rate_limit_reset_ms": 1655708401039,
    "rate_limit": 600
}
```

t(:account_para_getActive)

<aside class="warning">
t(:getOrderList_warning)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpoList>/private/v1/order/list/inverse</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|t(:row_parameter_order_status) |false |string |t(:account_row_comment_orderStatus) |
|direction |false |string |t(:row_comment_cursor_direction) |
|limit |false |integer |t(:row_comment_limit) |
|cursor |false |string |t(:row_comment_cursor) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |integer |t(:row_comment_userID) |
|position_idx |integer |t(:row_comment_position_idx) |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol) |
|t(:row_parameter_side) |string |t(:row_comment_side) |
|t(:row_parameter_order_type) |string |t(:row_comment_order_type) |
|price  |string |t(:row_comment_resp_price) |
|qty  |string |t(:row_response_comment_qty) |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|order_id |string |t(:account_row_comment_orderId) |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|leaves_qty |string |t(:row_comment_leaves_qty) |
|leaves_value |string |t(:row_comment_leaves_value) |
|cum_exec_qty |string |t(:linear_resp_field_cum_exec_qty)  |
|cum_exec_value |string |t(:linear_resp_field_cum_exec_value)  |
|cum_exec_fee |string |t(:linear_resp_field_cum_exec_fee)  |
|reject_reason |string |t(:row_comment_reject_reason)  |
|take_profit |number |t(:row_comment_take_profit)  |
|stop_loss |number |t(:row_comment_stop_loss)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by) |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by) |
|cursor |string |t(:row_comment_resp_cursor) |


### t(:cancelactive)
> t(:codequote_curlExample)

```console
curl https://openapi-testnet.zoomex.com/private/v1/order/cancel/inverse \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","order_id":"","timestamp":{timestamp},"sign":"{sign}"}'
```

```python
from pyzmx import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.cancel_active_order(
    symbol="BTCUSD",
    order_id="3bd1844f-f3c0-4e10-8c25-10fea03763f6"
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
        "user_id": 533285,
        "order_id": "bab79185-7759-48f3-a5f4-206808b6f1ec",
        "symbol": "BTCUSD",
        "side": "Buy",
        "order_type": "Limit",
        "price": 19500,
        "qty": 100,
        "time_in_force": "GoodTillCancel",
        "order_status": "New",
        "last_exec_time": 1655711524.37661,
        "last_exec_price": 0,
        "leaves_qty": 100,
        "cum_exec_qty": 0,
        "cum_exec_value": 0,
        "cum_exec_fee": 0,
        "reject_reason": "EC_NoError",
        "order_link_id": "IPBTC00001",
        "created_at": "2022-06-20T07:52:04.376Z",
        "updated_at": "2022-06-20T07:54:35.339Z",
        "take_profit": "",
        "stop_loss": "",
        "tp_trigger_by": "",
        "sl_trigger_by": ""
    },
    "time_now": "1655711675.340162",
    "rate_limit_status": 99,
    "rate_limit_reset_ms": 1655711675338,
    "rate_limit": 100
}
```

t(:account_para_cancelActive)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCancel>/private/v1/order/cancel/inverse</span></code>
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
|user_id |number |t(:row_comment_userID)  |
|order_id |string |t(:account_row_comment_orderId) |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_order_type) |string |t(:row_comment_order_type)  |
|t(:row_parameter_price) |number |t(:row_comment_resp_price)  |
|qty |number |t(:row_response_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce) |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|last_exec_time |string |t(:row_comment_last_exec_time)  |
|last_exec_price |string |t(:row_comment_last_exec_price)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|cum_exec_qty |number |t(:linear_resp_field_cum_exec_qty)  |
|cum_exec_value |number |t(:linear_resp_field_cum_exec_value)  |
|cum_exec_fee |number |t(:linear_resp_field_cum_exec_fee)  |
|reject_reason |string |t(:row_comment_reject_reason)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|take_profit |number |t(:row_comment_take_profit)  |
|stop_loss |number |t(:row_comment_stop_loss)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by) |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by) |

### t(:replaceactive)
> t(:codequote_curlExample)

```console
curl https://openapi-testnet.zoomex.com/private/v1/order/replace/inverse \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","order_id":"","timestamp":{timestamp},"sign":"{sign}"}'
```

```python
from pyzmx import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.replace_active_order(
    symbol="BTCUSD",
    order_id="efa44157-c355-4a98-b6d6-1d846a936b93"
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
<code><span id=vpoReplace>/private/v1/order/replace/inverse</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoReplace"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|order_id |false |string |t(:row_comment_order_id_replace) |
|order_link_id |false |string |t(:row_comment_order_link_id_replace) |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol). |
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
curl "https://openapi-testnet.zoomex.com/private/v1/position/list/inverse?api_key={api_key}&symbol=BTCUSD&timestamp={timestamp}&sign={sign}"
```

```python
from pyzmx import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.my_position(
    symbol="BTCUSD"
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
        "id": 27913,
        "user_id": 1,
        "risk_id": 1,
        "symbol": "BTCUSD",
        "side": "Buy",
        "size": 5,
        "position_value": "0.0006947",
        "entry_price": "7197.35137469",
        "is_isolated":true,
        "auto_add_margin": 0,
        "leverage": "1",
        "effective_leverage": "1",
        "position_margin": "0.0006947",
        "liq_price": "3608",
        "bust_price": "3599",
        "occ_closing_fee": "0.00000105",
        "occ_funding_fee": "0",
        "take_profit": "0",
        "stop_loss": "0",
        "trailing_stop": "0",
        "position_status": "Normal",
        "deleverage_indicator": 4,
        "oc_calc_data": "{\"blq\":2,\"blv\":\"0.0002941\",\"slq\":0,\"bmp\":6800.408,\"smp\":0,\"fq\":-5,\"fc\":-0.00029477,\"bv2c\":1.00225,\"sv2c\":1.0007575}",
        "order_margin": "0.00029477",
        "wallet_balance": "0.03000227",
        "realised_pnl": "-0.00000126",
        "unrealised_pnl": 0,
        "cum_realised_pnl": "-0.00001306",
        "cross_seq": 444081383,
        "position_seq": 287141589,
        "created_at": "2019-10-19T17:04:55Z",
        "updated_at": "2019-12-27T20:25:45.158767Z"
        "tp_sl_mode": "Partial"
    },
    "time_now": "1577480599.097287",
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1580885703683,
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
            "is_valid": true,
            "data": {
                "id": 0,
                "position_idx": 0,
                "mode": 0,
                "user_id": 118921,
                "risk_id": 1,
                "symbol": "BTCUSD",
                "side": "Buy",
                "size": 10,
                "position_value": "0.00076448",
                "entry_price": "13080.78694014",
                "is_isolated": false,
                "auto_add_margin": 1,
                "leverage": "100",
                "effective_leverage": "0.01",
                "position_margin": "0.40111704",
                "liq_price": "25",
                "bust_price": "25",
                "occ_closing_fee": "0.0003",
                "occ_funding_fee": "0",
                "take_profit": "0",
                "stop_loss": "0",
                "trailing_stop": "0",
                "position_status": "Normal",
                "deleverage_indicator": 1,
                "oc_calc_data": "{\"blq\":0,\"slq\":0,\"bmp\":0,\"smp\":0,\"fq\":-10,\"bv2c\":0.0115075,\"sv2c\":0.0114925}",
                "order_margin": "0",
                "wallet_balance": "0.40141704",
                "realised_pnl": "-0.00000008",
                "unrealised_pnl": 0.00003797,
                "cum_realised_pnl": "-0.090626",
                "cross_seq": 764786721,
                "position_seq": 581513847,
                "created_at": "2020-08-10T07:04:32Z",
                "updated_at": "2020-11-02T00:00:11.943371457Z"
                "tp_sl_mode": "Partial"
            }
        },
        ...
        {
            "is_valid": true,
            "data": {
                "id": 0,
                "position_idx": 0,
                "mode": 0,
                "user_id": 118921,
                "risk_id": 35,
                "symbol": "XRPUSD",
                "side": "None",
                "size": 0,
                "position_value": "0",
                "entry_price": "0",
                "is_isolated": false,
                "auto_add_margin": 1,
                "leverage": "16.67",
                "effective_leverage": "16.67",
                "position_margin": "0",
                "liq_price": "0",
                "bust_price": "0",
                "occ_closing_fee": "0",
                "occ_funding_fee": "0",
                "take_profit": "0",
                "stop_loss": "0",
                "trailing_stop": "0",
                "position_status": "Normal",
                "deleverage_indicator": 0,
                "oc_calc_data": "{\"blq\":0,\"slq\":0,\"bmp\":0,\"smp\":0,\"bv2c\":0.06153301,\"sv2c\":0.06144302}",
                "order_margin": "0",
                "wallet_balance": "0",
                "realised_pnl": "0",
                "unrealised_pnl": 0,
                "cum_realised_pnl": "0",
                "cross_seq": -1,
                "position_seq": 352149441,
                "created_at": "2020-08-10T07:04:32Z",
                "updated_at": "2020-08-22T08:06:32Z"
                "tp_sl_mode": "Partial"
            }
        }
    ],
    "time_now": "1604302124.031104",
    "rate_limit_status": 118,
    "rate_limit_reset_ms": 1604302124020,
    "rate_limit": 120
}
```

t(:account_para_myPosition)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=pList>/private/v1/position/list/inverse</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |false |string |t(:row_comment_symbol)    |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id |number |t(:row_comment_position_id)  |
|position_idx |integer |t(:row_comment_position_idx)  |
|mode |number |t(:row_comment_position_mode)  |
|user_id |number |t(:row_comment_userID)  |
|risk_id |number |t(:row_comment_riskId)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|size |number |t(:row_comment_position_size)  |
|position_value |string |t(:row_comment_position_value)  |
|entry_price |string |t(:row_comment_entry_price)  |
|is_isolated | bool | t(:row_comment_isolated) |
|auto_add_margin |number |t(:row_comment_auto_add_margin)  |
|leverage |string |t(:resp_field_leverage)  |
|effective_leverage |string |t(:row_comment_effective_leverage)  |
|position_margin |string |t(:row_comment_position_margin)  |
|liq_price |string |t(:row_comment_liq_price)  |
|bust_price |string |t(:row_comment_bust_price)  |
|occ_closing_fee |string |t(:row_comment_occ_closing_fee)  |
|occ_funding_fee |string |t(:row_comment_occ_funding_fee)  |
|take_profit |string |t(:row_comment_take_profit)  |
|stop_loss |string |t(:row_comment_stop_loss)  |
|trailing_stop |string |t(:row_comment_trailing_stop)  |
|position_status |string |t(:row_comment_position_status)  |
|deleverage_indicator |number |t(:row_comment_deleverage_indicator)  |
|oc_calc_data |string |t(:row_comment_oc_calc_data)  |
|order_margin |string |t(:row_comment_order_margin)  |
|wallet_balance |string |t(:row_comment_wallet_balance)  |
|realised_pnl |string |t(:row_comment_realised_pnl)  |
|unrealised_pnl |number |t(:row_comment_unrealised_pnl)  |
|cum_realised_pnl |string |t(:row_comment_cum_realised_pnl)  |
|cross_seq |number |t(:row_comment_cross_seq)  |
|position_seq |number |t(:row_comment_position_seq)  |
|created_at |string |t(:row_comment_created_at_position)  |
|updated_at |string |t(:row_comment_updated_at)  |
|t(:row_parameter_tp_sl_mode) |string |t(:linear_resp_tp_sl_mode)  |

### t(:switchmode)

> t(:codequote_curlExample)

```python
from pyzmx import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.full_partial_position_tp_sl_switch(
    symbol="BTCUSD",
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
<code><span id=vptSwitchMode>/private/v1/tpsl/switch-mode/inverse</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vptSwitchMode"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

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
curl https://openapi-testnet.zoomex.com/private/v1/position/trading-stop/inverse \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","stop_loss":7000,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python
from pyzmx import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.set_trading_stop(
    symbol="BTCUSD",
    stop_loss=7000
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
        "id": 0,
        "user_id": 533285,
        "symbol": "BTCUSD",
        "side": "Buy",
        "size": 400,
        "position_value": 0.019995,
        "entry_price": 20005.00125031,
        "risk_id": 1,
        "auto_add_margin": 0,
        "leverage": 2,
        "position_margin": 0.0099975,
        "liq_price": 13381.5,
        "bust_price": 13337,
        "occ_closing_fee": 0.000018,
        "occ_funding_fee": 0,
        "take_profit": 26000,
        "stop_loss": 14000,
        "trailing_stop": 0,
        "position_status": "Normal",
        "deleverage_indicator": 4,
        "oc_calc_data": "{\"blq\":100,\"blv\":\"0.00588235\",\"slq\":0,\"bmp\":17000.0085,\"smp\":0,\"fq\":-400,\"fc\":-0.00295,\"bv2c\":0.5015,\"sv2c\":0.5009}",
        "order_margin": 0.00295,
        "wallet_balance": 0.3999834,
        "realised_pnl": 0,
        "cum_realised_pnl": -0.00000526,
        "cum_commission": 0,
        "cross_seq": 5208583955,
        "position_seq": 0,
        "created_at": "2022-06-09T07:14:33.264474461Z",
        "updated_at": "2022-06-21T04:08:10.185159763Z",
        "ext_fields": {
            "trailing_active": "0",
            "sl_trigger_by": "LastPrice",
            "tp_trigger_by": "LastPrice",
            "v": 10151,
            "mm": 0
        }
    },
    "time_now": "1655784490.185727",
    "rate_limit_status": 74,
    "rate_limit_reset_ms": 1655784490182,
    "rate_limit": 75
}
```

t(:account_para_tradingStop)

<aside class="notice">
t(:account_aside_tradingStop)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=oapTradingStopNew>/private/v1/position/trading-stop/inverse</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oapTradingStopNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|take_profit |false |number |t(:account_row_comment_takeProfit) |
|stop_loss |false |number |t(:account_row_comment_stopLoss) |
|trailing_stop |false |number |t(:account_row_comment_trailingStop) |
|t(:row_parameter_tp_trigger_by) | false | string | t(:account_row_comment_tp_trigger_by)
|t(:row_parameter_sl_trigger_by) | false | string | t(:account_row_comment_sl_trigger_by)
|new_trailing_active |false |number |t(:account_row_comment_trailingStop_active) |
|sl_size |false |number |t(:row_comment_sl_size) |
|tp_size |false |number |t(:row_comment_tp_size) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id |number |t(:row_comment_position_id)  |
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|size |number |t(:row_comment_position_size)  |
|position_value |number |t(:row_comment_position_value)  |
|entry_price |number |t(:row_comment_entry_price)  |
|risk_id |number |t(:row_comment_riskId)  |
|auto_add_margin |number |t(:row_comment_auto_add_margin)  |
|leverage |number |t(:resp_field_leverage)  |
|position_margin |number |t(:row_comment_position_margin)  |
|liq_price |number |t(:row_comment_liq_price)  |
|bust_price |number |t(:row_comment_bust_price)  |
|occ_closing_fee |number |t(:row_comment_occ_closing_fee)  |
|occ_funding_fee |number |t(:row_comment_occ_funding_fee)  |
|take_profit |number |t(:row_comment_take_profit)  |
|stop_loss |number |t(:row_comment_stop_loss)  |
|trailing_stop |number |t(:row_comment_trailing_stop)  |
|position_status |string |t(:row_comment_position_status)  |
|deleverage_indicator |number |t(:row_comment_deleverage_indicator)  |
|oc_calc_data |map |t(:row_comment_oc_calc_data)  |
|order_margin |number |t(:row_comment_order_margin)  |
|wallet_balance |number |t(:row_comment_wallet_balance)  |
|realised_pnl |number |t(:row_comment_realised_pnl)  |
|cum_realised_pnl |number |t(:row_comment_cum_realised_pnl)  |
|cum_commission |number |t(:row_comment_cum_commission)  |
|cross_seq |number |t(:row_comment_cross_seq)  |
|position_seq |number |t(:row_comment_position_seq)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|trailing_active |string |t(:row_comment_trailing_active)  |
|t(:row_parameter_sl_trigger_by) |string |t(:row_comment_sl_trigger_by)  |
|t(:row_parameter_tp_trigger_by) |string |t(:row_comment_tp_trigger_by)  |

### t(:changemargin)
> t(:codequote_curlExample)

```console
curl https://openapi-testnet.zoomex.com/private/v1/position/change-position-margin/inverse \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD",margin:"10","timestamp":{timestamp},"sign":"{sign}"}'
```

```python
from pyzmx import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.change_margin(
    symbol="BTCUSD",
    margin=0.00001
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": 0.00000997,
    "ext_info": null,
    "time_now": "1577480720.003444",
    "rate_limit_status": 74,
    "rate_limit_reset_ms": 1577480720011,
    "rate_limit": 75
}
```

t(:account_para_changeMargin)

<aside class="notice">
t(:account_aside_changeMargin)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pChangePositionMarginNew>/private/v1/position/change-position-margin/inverse</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pChangePositionMarginNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|margin |<b>true</b> |string |t(:row_comment_margin)  |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|result |number |t(:row_comment_margin_result)  |

### t(:setleverage)
> t(:codequote_curlExample)

```console
curl https://openapi-testnet.zoomex.com/private/v1/position/leverage/save/inverse \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","leverage":14,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python
from pyzmx import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.set_leverage(
    symbol="BTCUSD",
    leverage=2
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": 2,
    "ext_info": null,
    "time_now": "1577477968.175013",
    "rate_limit_status": 74,
    "rate_limit_reset_ms": 1577477968183,
    "rate_limit": 75
}
```

t(:linear_account_para_setLeverage)

<aside class="notice">
t(:account_aside_setleverage)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=ulSaveNew>/private/v1/position/leverage/save/inverse</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ulSaveNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|leverage |<b>true</b> |number |t(:row_comment_leverage_old) |
|leverage_only |false |bool |t(:row_comment_leverage_only) |
<!--
|buy_leverage |<b>true</b> |number |t(:futures_row_comment_leverage) |
|sell_leverage |<b>true</b> |number |t(:futures_row_comment_leverage) |
-->

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|result |number |t(:row_comment_leverage_result)  |

## t(:risklimit)
### t(:getrisklimit)
> t(:codequote_curlExample)

```console
curl "https://openapi-testnet.zoomex.com/public/v1/risk-limit/list/inverse?symbol=BTCUSD"
```

```python
from pyzmx import inverse_perpetual
session_unauth = inverse_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com"
)
print(session_unauth.get_risk_limit(
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
            "id": 11,
            "is_lowest_risk": 1,
            "section": [
                "1",
                "2",
                "3",
                "5",
                "10",
                "25",
                "50",
                "100"
            ],
            "symbol": "ETHUSD",
            "limit": 500,
            "max_leverage": "100",
            "starting_margin": "1",
            "maintain_margin": "0.5",
            "coin": "ETH",
            "created_at": "",
            "updated_at": ""
        },
        ...
        {
            "id": 21,
            "is_lowest_risk": 0,
            "section": [
                "1",
                "2",
                "3",
                "4",
                "5",
                "7",
                "8",
                "9"
            ],
            "symbol": "ETHUSD",
            "limit": 30000,
            "max_leverage": "9.1",
            "starting_margin": "11",
            "maintain_margin": "5.5",
            "coin": "ETH",
            "created_at": "",
            "updated_at": ""
        }
    ],
    "ext_code": "",
    "ext_info": "",
    "time_now": "1662629588.663921"
}
```

t(:account_para_getRisk)

<aside class="notice">
t(:account_aside_getRisk_inverse)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oawrlList>/public/v1/risk-limit/list/inverse</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawrlList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>false</b> |string |t(:row_comment_symbol) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id |number |t(:row_comment_riskId)  |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)  |
|limit |number |t(:row_comment_risk_limit)    |
|maintain_margin |number |t(:row_comment_maintain_margin)  |
|starting_margin |number |t(:row_comment_starting_margin_inverse)  |
|section |string |t(:row_comment_section)  |
|is_lowest_risk |number |t(:row_comment_is_lowest_risk)    |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|max_leverage |string |t(:row_comment_max_leverage)  |


### t(:setrisklimit)
> t(:codequote_curlExample)

```console
curl https://openapi-testnet.zoomex.com/private/v1/position/risk-limit/inverse \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","risk_id":2,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python
from pyzmx import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.set_risk_limit(
    symbol="BTCUSD",
    risk_id=2
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
    "time_now": "1620283810.393787",
    "token": null
}
```

<aside class="notice">
t(:account_aside_getRisk_inverse)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=oawrlList>/private/v1/position/risk-limit/inverse</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawrlList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|risk_id |<b>true</b> |integer |t(:row_comment_riskId) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|risk_id |number |t(:row_comment_riskId)  |

