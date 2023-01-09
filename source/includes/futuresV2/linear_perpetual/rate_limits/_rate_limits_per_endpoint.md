## t(:understandingratelimits)
t(:rate_para_understanding)

```
"rate_limit_status": 119,
"rate_limit_reset_ms": 1572114055663,
"rate_limit": 120
```

* `rate_limit_status` - t(:rate_text_limitStatus_understanding)
* `rate_limit` - t(:rate_text_limit_understanding)
* `rate_limit_reset_ms` - t(:rate_text_limitReset)


### t(:perendpoint)
<table class="custom_table">
  <tr>
    <th>t(:row_comment_rate_limit)</th>
    <th>t(:row_comment_path)</th>
    <th>t(:row_comment_consume)</th>
  </tr>
  <tr>
    <td rowspan="3">100/min</td>
    <td>/private/v1/order/create/usdt </td>
    <td>1 / request</td>
  </tr>
  <tr><td>/private/v1/order/replace/usdt </td><td>1 / request</td></tr>
  <tr><td>/private/v1/order/cancel/usdt </td><td>1 / request</td></tr>
 <tr>
    <td rowspan="4">75/min</td>
    <td>/private/v1/position/set-leverage/usdt   </td>
    <td>1 / request</td>
  </tr>
  <tr><td>/private/v1/tpsl/switch-mode/usdt </td><td>1 / request</td></tr>
  <tr><td>/private/v1/position/trading-stop/usdt </td><td>1 / request</td></tr>
  <tr><td>/private/v1/position/add-margin/usdt </td><td>1 / request</td></tr>

  <tr>
    <td rowspan="1">120/min</td>
    <td>/private/v1/position/list/usdt  </td>
    <td>1 / request</td>
  </tr>
 
  <tr>
    <td rowspan="1">600/min</td>
    <td>/private/v1/order/list/usdt </td>
    <td>1 / request</td>
  </tr>
  
</table>
