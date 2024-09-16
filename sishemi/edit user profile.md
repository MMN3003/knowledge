add these data to http://[::1]:3000/doc/v1/#/User%20%5BAdmin%5D/AdminV1UserController_GetUserProfile api
- [x] Joined Date : `first_login` in users collection
- [-] T&C : Accepted   `accept_legal` already exist
- [-] Admin T&C :   `accept_admin_terms` already exist
- [x] KWS for UnderAges : email and status  
	- [-] `parent_email`:already exist
	- [x] status: in `parent_email_data` of users collection
	  ```json
{
"name": "parent-verified",
"time": "2024-04-15T13:37:47.158Z",
"orgId": "0dc58714-cc1c-4896-9d8d-62a74d05957c",
"productId": "60915b01-3965-45d4-b814-6f29d544951c",
"payload": {
"parentEmail": "ehsan@imadev.team",
"externalPayload": "{\"user_id\":\"661d2d66193e1b98e1b18a67\"}",
"status": {
"verified": true,
"transactionId": "pqr678",
"_id": "661d2dac193e1b98e1b18a84"
},
"_id": "661d2dac193e1b98e1b18a83"
},
"_id": "661d2dac193e1b98e1b18a82"
}
```
- [x] Subscription cycle date: `admin_until_date` in users collection 
- [x] user team leadership count
- [ ] Organization lists of user
