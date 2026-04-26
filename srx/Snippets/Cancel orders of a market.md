This is an example of http api to `apigateway` service for cancel order of a market.
make sure to get all users uuid that have at least one open order in this market.
Get list of user from `matchengine` => `exchange_log` database => `order_slice` table . make sure close market for at least one hour then select users from this table, `order_slice` sync each one hour!

```bash
  

curl --location --request POST 'http://localhost:9009/bpapi/v1/mng/markets/cancel-all-orders' \

--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJicm9rZXJfaWQiOiIzIiwiZXhwIjoxODMxMTA4OTkzfQ.4JxFKCZdQado_VrAI-mzsHuWlrBRIkj_ytaNMmlfg7A' \

--header 'Content-Type: application/json' \

--data-raw '{

"users": [

"9c2b04bc-1f3a-4a5e-84c6-9a3e6b7e2e22",

],

"market_name": "USDT_IRT",

"broker_id": "2"

}'
```


"e10dd2d0-1d54-11ed-a350-d45d64bd0ed5"
