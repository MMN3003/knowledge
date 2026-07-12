``` sql
SELECT * from public.deposits

WHERE client_tracking_id LIKE 'dp-%' and id not in

('4a94dff5-8a69-43c5-8e5c-34d64d33b554','f3fe02be-ab04-497e-8a2d-fca18b3d5465',

'a0c6c803-2124-41bb-90a0-db7e95203f38','e1438ebe-bfbf-441e-86c0-8008181d351e',

'd6714c32-8f96-4e9a-8483-4968b9b002b4','896eec0a-5f51-4b48-8354-32d6fb48fe5d',

'8ec78748-8f93-484f-b822-3270c92eea22','92c9ae64-e0e0-4dd5-9e11-513ccda7c028',

'28d3426b-e25a-41d0-98b8-3dd5b25d5690','59d98412-646f-47dc-8a52-112131e4e829',

'0ad66298-9a50-42a0-843a-14da0680fddb'

)
```