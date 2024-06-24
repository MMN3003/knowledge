### channels
- **One-to-many**, also known as fan out. This is where multiple subscribers receive one message. For example, an application that updates sports fans with game updates, or one that provides travelers with public transport times and status.
- **Many-to-one**, where multiple publishers send messages to one subscriber. For example, an application monitoring temperature in multiple locations, or one that publishes the location of company vehicles to headquarters.
- **Many-to-many**, where the number of publishers and subscribers varies. For example, chat applications where direct messaging between two users would use a channel, and a company-wide group chat would use another.
### messages history
- 2 minutes memory
- 72 hours on disk
- for more we have to store messages in our database
	- [webhook](https://ably.com/docs/general/webhooks)
### presence
Ably’s [presence](https://ably.com/docs/presence-occupancy) feature enables clients to be aware of other clients that are currently “present” on a channel.
- client joins
- client leave
- client update an optional payload like status "out for lunch"

### Push notifications
 - send message to users through FCM
	 - You can publish push notifications to user devices [directly](https://ably.com/docs/push/publish#direct-publishing) or [via channels](https://ably.com/docs/push/publish#via-channels).