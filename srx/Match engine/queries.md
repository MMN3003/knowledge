```sql
SELECT

u.user_id,

  

COUNT(*) AS trade_count,

  

SUM(u.amount) AS total_amount,

  

SUM(u.price * u.amount) AS user_total_value,

  

SUM(b.market_price * u.amount) AS market_total_value,

  

SUM((u.price * u.amount) - (b.market_price * u.amount)) AS total_diff,

SUM(ABS((u.price * u.amount) - (b.market_price * u.amount))) AS total_diff_percent,

  

  

AVG(

((u.price - b.market_price) / NULLIF(b.market_price,0)) * 100

) AS avg_price_diff_percent,

  

MAX(

ABS((u.price - b.market_price) / NULLIF(b.market_price,0) * 100)

) AS max_price_diff_percent

  

FROM user_trade u

JOIN balance_history b

ON u.trade_id::text = b.business_id

  

WHERE u.id > 56971117

AND u.broker_id = '3'

AND u.market IN (

'PEANUT_USDT',

'DUCKY_USDT',

'APES_USDT',

'SMILEK_USDT'

)

AND ABS((u.price - b.market_price) / NULLIF(b.market_price,0) * 100) > 20

  

GROUP BY u.user_id

  

ORDER BY total_diff_percent DESC;
```

```sql
SELECT

u.id,

u.user_id,

u.trade_id,

u.market,

u.amount,

b.asset,

u.price AS user_price,

b.market_price,

  

ROUND(

((u.price - b.market_price) / NULLIF(b.market_price,0)) * 100,

4

) AS price_diff_percent,

  

(u.price * u.amount) AS user_total,

(b.market_price * u.amount) AS market_total,

  

((u.price * u.amount) - (b.market_price * u.amount)) AS total_diff

  

FROM user_trade u

JOIN balance_history b

ON u.trade_id::text = b.business_id

  

WHERE u.id > 56971117

AND u.broker_id = '3'

AND u.market IN (

'PEANUT_USDT',

'DUCKY_USDT',

'APES_USDT',

'SMILEK_USDT'

)

AND ABS((u.price - b.market_price) / NULLIF(b.market_price,0) * 100) > 1

  

ORDER BY ABS((u.price - b.market_price) / NULLIF(b.market_price,0) * 100) DESC;
```

```sql
SELECT

u.id,

u.trade_id,

u.market,

u.amount,

b.asset,

u.price AS user_price,

b.market_price,

  

ROUND(

((u.price - b.market_price) / NULLIF(b.market_price,0)) * 100,

4

) AS price_diff_percent,

  

(u.price * u.amount) AS user_total,

(b.market_price * u.amount) AS market_total,

  

((u.price * u.amount) - (b.market_price * u.amount)) AS total_diff

  

FROM user_trade u

JOIN balance_history b

ON u.trade_id = b.business_id

WHERE u.id > 56971117

AND u.market IN (

'PEANUT_USDT',

'DUCKY_USDT',

'APES_USDT',

'SMILEK_USDT'

);
```
