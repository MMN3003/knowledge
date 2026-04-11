```bash
  

curl --location --request POST 'http://localhost:9009/bpapi/v1/mng/markets/cancel-all-orders' \

--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJicm9rZXJfaWQiOiIzIiwiZXhwIjoxODMxMTA4OTkzfQ.4JxFKCZdQado_VrAI-mzsHuWlrBRIkj_ytaNMmlfg7A' \

--header 'Content-Type: application/json' \

--data-raw '{

"users": [

"5291d963-1f48-4d56-918c-2719f40303f8",

"b941a81b-1193-4e6e-8ec8-fccdd0c3722c",

"d6851441-7e94-459d-b106-c3141a31cc56",

"913f2938-b4b2-4bea-9031-e587ac224cbe",

"bfa262d4-4390-4ec3-b4b3-4453169e770f",

"f7eb294c-85b0-4744-aaec-3e147aadd2dd",

"45121dbf-b2fe-477f-8c13-ce73bd2ee100",

"5291d963-1f48-4d56-918c-2719f40303f8",

"5291d963-1f48-4d56-918c-2719f40303f8",

"0f05449a-1d55-11ed-a350-d45d64bd0ed5",

"b511a39d-7550-434f-ab83-662213034454",

"1f7740b9-6214-47cf-998b-c486bd663ee0",

"e882fe46-e24c-48fa-b098-3c80470729cb",

"6e1c1f73-2e74-490d-b7d4-56d5b47b0d40",

"ec1f5b29-7d81-4b02-ae51-8706e5806271",

"8e9bd0ec-6998-4ddc-b98c-187f3f4d68fe",

"a1459a57-f78b-423f-b007-fdb54e351fbe",

"dcc51011-fad1-4f2c-b5af-86a02ce91c9a",

"ac672760-7131-44b0-87ff-e23bb6dfcc0d",

"74081a02-0852-4b4d-96dc-b087232243e6",

"26add063-db3c-471f-adb6-394ee5e2a3a2",

"adb5a248-d8a6-4d22-a30b-c87697c1add0",

"1468a985-1d55-11ed-a350-d45d64bd0ed5",

"242e5bd3-2356-4f9f-b524-77a932cb2aa9",

"2f37508d-51d3-4aed-802b-5cd4c8243dc4",

"242e5bd3-2356-4f9f-b524-77a932cb2aa9",

"9d4b68e0-69c8-4cd4-91ed-6cb77477183f",

"242e5bd3-2356-4f9f-b524-77a932cb2aa9",

"fd83801d-7b27-4114-9b12-0574304f0f35",

"1468a985-1d55-11ed-a350-d45d64bd0ed5",

"86afb64d-2b8d-4231-b3c7-d5c9ecec8d34",

"a1459a57-f78b-423f-b007-fdb54e351fbe"

],

"market_name": "PEANUT_IRT",

"broker_id": "3"

}'
```