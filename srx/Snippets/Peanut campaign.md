# Users Deposits
```sql
select user_id,business,sum(change) as change from balance_history where

asset <>'PEANUT' and business in ('OFFLINE_PAYMENT','deposit_detection') and

user_id in

(

'31bc8eb0-4768-4b3a-898c-00c5f181acb9',

'16f3094d-029b-4a7e-8de7-e46233030fd9',
'1b48dd88-bd05-4b4d-9549-4fa2962226ac')

group by 1,2
```
select all users that register after 2026/03/25