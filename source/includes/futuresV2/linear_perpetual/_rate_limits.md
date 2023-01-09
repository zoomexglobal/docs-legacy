# t(:ratelimits)
### t(:ipratelimits)
t(:ip_rate_para_understanding)

### t(:understandingratelimits)
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
    <td rowspan="8">100/min</td>
    <td>/private/v1/order/create/usdt </td>
    <td>1 / request</td>
  </tr>
  <tr><td>/private/v1/order/replace/usdt </td><td>1 / request</td></tr>
  <tr><td>/private/v1/order/cancel/usdt </td><td>1 / request</td></tr>
  <tr><td>/private/v1/order/cancel/usdt-all </td><td>10 / request</td></tr>
   <tr>
    <td rowspan="6">75/min</td>
    <td>/private/v1/position/set-leverage/usdt   </td>
    <td>1 / request</td>
  </tr>
  <tr><td>/private/v1/tpsl/switch-mode/usdt </td><td>1 / request</td></tr>
  <tr><td>/private/v1/position/trading-stop/usdt </td><td>1 / request</td></tr>
  <tr><td>/private/v1/position/add-margin/usdt </td><td>1 / request</td></tr>
    
  <tr>
    <td rowspan="4">120/min</td>
    <td>/private/v1/position/list/usdt  </td>
    <td>1 / request</td>
  </tr>
  <tr>
    <td rowspan="4">600/min</td>
    <td>/private/v1/order/list/usdt </td>
    <td>1 / request</td>
  </tr>

 </table>

### t(:orderlimits)
t(:rate_para_limits)

### t(:raisemylimit)
t(:rate_para_raise)

### t(:liquidity)
t(:rate_para_liquidity)

#### t(:ofrthreshold)
t(:rate_para_threshold)

##### t(:ofrratio)
t(:rate_para_ratio)

##### t(:ofrratioExample)


<pre class="center-column-nonindent">
t(:rate_pre_ratioExampleA)
</pre>

<pre class="center-column-nonindent">
t(:rate_pre_ratioExampleB)
</pre>


##### t(:ofrminimum)
t(:rate_para_minimum)


#### t(:frequencylimit)
t(:rate_para_frequency)


| t(:column_LCP) | t(:column_frequencyLimit) |
| ----    | ----  |
| 20-100  | t(:row_frequencyLimit_800) |
| 10-20   | t(:row_frequencyLimit_600) |
| 5-10    | t(:row_frequencyLimit_400) |
| 2-5     | t(:row_frequencyLimit_200) |
| <2      | t(:row_frequencyLimit_100) |

##### t(:liquidityPoints)
t(:rate_para_liquidityPoints)

##### t(:ratelimitsexplanation)

###### t(:pricerange)
t(:rate_para_priceRange)

###### t(:pricerangeExample)
<pre class="center-column-nonindent">
t(:rate_pre_priceRangeExample)
</pre>


###### t(:pou)
t(:rate_para_POU)

<pre class="center-column-nonindent">
t(:rate_pre_POUExample)
</pre>


###### t(:poa)
t(:rate_para_POA)

###### t(:poaExample)
t(:rate_para_POAExample)

<pre class="center-column-nonindent">
t(:rate_pre_POAExample)
</pre>

<aside class="notice">
t(:rate_aside_POAExample)
</aside>
