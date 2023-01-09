# t(:api)
t(:api_para)

### t(:servertime)
> t(:codequote_curlExample)

```console
curl https://openapi-testnet.zoomex.com/public/v1/time
```

```python
from pyzmx import inverse_perpetual
session_unauth = inverse_perpetual.HTTP(
    endpoint="https://openapi-testnet.zoomex.com"
)
print(session_unauth.server_time())  
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {},
    "time_now": "1577444332.192859"
}
```
t(:api_para_time)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpTime>/public/v1/time</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpTime"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
