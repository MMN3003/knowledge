### channels
- **One-to-many**, also known as fan out. This is where multiple subscribers receive one message. For example, an application that updates sports fans with game updates, or one that provides travelers with public transport times and status.
- **Many-to-one**, where multiple publishers send messages to one subscriber. For example, an application monitoring temperature in multiple locations, or one that publishes the location of company vehicles to headquarters.
- **Many-to-many**, where the number of publishers and subscribers varies. For example, chat applications where direct messaging between two users would use a channel, and a company-wide group chat would use another.
### history
- 2 minutes memory
- 72 hours on disk
- for more