```
curl -X POST "http://localhost:9009/dapi/v1/chainpulse/wallet/activate-onchain" \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJicm9rZXJfaWQiOiIzIiwiZXhwIjoxODMxMTA4OTkzfQ.4JxFKCZdQado_VrAI-mzsHuWlrBRIkj_ytaNMmlfg7A' \
    -H "Content-Type: application/json" \
    -d '{"wallet_id": "223397"}'
```