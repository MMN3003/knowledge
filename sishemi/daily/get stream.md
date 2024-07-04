add create user token every where that user want to get our app token
add server side token to env and use it in creating channel and other things.

flash is one direction channel
team or organization is 
group is bi directional many to many

first step => auth 5 times
- '/oauth/refresh-token'

- in user register => create user in get stream 
	- user id
	- nickname => username
	- full name => display name
	- avatar => random avatar image
	- birth date
	- blue check mark
- edit user
	- avatar
	- full name =>
	- username
- ban user
	- deactivate user in `getstream` (maybe leave all groups and channels )
	- change user status to banned
- activate banned user
	- activate user in `getstream` (maybe join all channels and groups again)
	- change user status to active
- create group and channel(flash) 
	- channel public/private
		- in public channel every team user must added to channel
		- every one who join the team will join to public channels
		- in creating flash add users by flash role except admins and moderators
	- admin(co-leader) that added by owner can create flash or group
- edit flash and group
	- add or remove admin
	- add or remove picture
	- add or remove category of sport list or general(all)
- direct
	- search user 
	- create group and add these two people
	- add meta data direct to group
- delete flash and group
- web hook changes
- active fence call our web hook to delete a message
- general group of ima by each category sport
	- add user to these groups in register as member
		- queue
