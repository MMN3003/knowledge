In order to load new changes in coins or market, `matchengine` should reload and fetch them. this is the api that reload `matchengine`:
```bash
curl --location --request GET 'localhost:9009/bpapi/v1/mng/markets/reload' --header 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJicm9rZXJfaWQiOiIzIiwiZXhwIjoxODMxMTA4OTkzfQ.4JxFKCZdQado_VrAI-mzsHuWlrBRIkj_ytaNMmlfg7A'
```

Token should be taken from `internal wallet` env file.