add create user token every where that user want to get our app token
add server side token to env and use it in creating channel and other things.

flash is one direction channel
team or organization is 
group is bi directional many to many

first step => auth 5 times
- @Post('/oauth/refresh-token')
- @Post('/oauth/token')




- block and unblock later
- dont send them fcm to all admin leave an other admins
- sort of teams by user role in get teams
- delete account move from client to admins



- get list of team admins that are not admin channel
- 
- registery
	- mobile mifreste
	- verify otp
	- set information user client
- update user
	- patch profile update
-  check category of sport list change to array of id in create channel
- join  leave to getstream channel
- add or remove moderator or admin
- 
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
- create group and channel(flash) 
	- channel public/private
		- in public channel every team user must added to channel
		- every one who join the team will join to public channels
		- in creating flash add users by flash role except admins and moderators
	- admin(co-leader) that added by owner can create flash or group
- ban user
	- deactivate user in `getstream` (maybe leave all groups and channels )
	- change user status to banned
- activate banned user
	- activate user in `getstream` (maybe join all channels and groups again)
	- change user status to active

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








create falsh or group public
	- add every one to members
	- then add admins to moderators after create 
as admin or coleader 
	- creator admin of team has to be in every channels and group of a team
	- creator admin of team can not remove him self from channels and group of a team


direct => channel message type only those two of them must be owner 





----------------------------------------
transfer all data from send bird to getstream
