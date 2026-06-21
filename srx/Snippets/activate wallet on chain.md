```
curl --request POST \
  --url https://core.sarmayex.com/dapi/v1/chainpulse/wallet/activate-onchain \
  --header 'accept: application/json' \
  --header 'accept-language: fa' \
  --header 'authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6Ijc4NzNmNjEyLWVkNzQtNDM4Mi1iNDA3LWQxODljNTA2Yzc2YSIsImV4cCI6MTc4MjA1MjI5N30.u2JLt_DHLP-0MJgNeIU9eqJKyF6v7Wq6We86ipT6DHo' \
  --header 'content-type: application/json' \
  --header 'origin: https://portal.srxx.org' \
  --header 'priority: u=1, i' \
  --header 'referer: https://portal.srxx.org/' \
  --header 'sec-ch-ua: "Google Chrome";v="149", "Chromium";v="149", "Not)A;Brand";v="24"' \
  --header 'sec-ch-ua-mobile: ?1' \
  --header 'sec-ch-ua-platform: "iOS"' \
  --header 'sec-fetch-dest: empty' \
  --header 'sec-fetch-mode: cors' \
  --header 'sec-fetch-site: cross-site' \
  --header 'user-agent: Mozilla/5.0 (iPhone; CPU iPhone OS 18_5 like Mac OS X) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/18.5 Mobile/15E148 Safari/604.1' \
  --data '{
  "wallet_id": "223397"
}'
```

get wallet id from wallets table of chainpulse 
get token from portal panel