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
    <td rowspan="4">100/min</td>  
  </tr>
  <tr><td>/private/v1/order/cancel/inverse       </td><td>1 / request</td></tr>
  <tr><td>/private/v1/order/replace/inverse      </td><td>1 / request</td></tr>
  <tr><td>/private/v1/order/create/inverse     </td><td>1 / request</td></tr>
  <tr>
    <td rowspan="1">600/min</td>
    <td>/private/v1/order/list/inverse </td>
    <td>1 / request</td>
  </tr>
  <tr>
    <td rowspan="4">75/min</td>
    <td>/private/v1//position/leverage/save/inverse </td>
    <td>1 / request</td>
  </tr>
  <tr><td>/private/v1/position/change-position-margin/inverse</td><td>1 / request</td></tr>
  <tr><td>/private/v1/position/trading-stop/inverse</td><td>1 / request</td></tr>
  <tr><td>/private/v1/tpsl/switch-mode/inverse</td><td>1 / request</td></tr>
  <tr>
    <td rowspan="3">120/min</td>
  </tr>
  <tr><td>/private/v1/position/list/inverse</td><td>1 / request</td></tr>

</table>
