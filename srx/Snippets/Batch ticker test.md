```bash
curl --location --request POST "https://exhub.atozcrypto.net/api/v1/kucoin/batch-tickers" \

--header 'Content-Type: application/json' \

--data-raw '{

"pairs": [{"base_asset":"TON","quote_asset":"USDT"},{"base_asset":"BTC","quote_asset":"USDT"}]

}'
```
Test batch ticker api of `exhub` that currently used in `algo` bot for market making.