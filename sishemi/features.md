- [ ]  share event in app and like organization
- [ ] add post with event calendar
- [ ] entry price to  match in event
- [ ] donate money to a team
	- [ ] donate list
	- [ ] how to withdraw
	- [ ] where to set withdrawal information
	- [ ] who can withdraw money
- [ ] follow user 
- [ ] create home feed from user followed or teams followed by user
- [ ] search coach and team by name city sport category fan count, member count
- [ ] add coach history and team honors
- [ ] user profile like linkedin
- [ ] show calenders event of chat in chats like a message
- [ ] show invite list for user 
- [ ] do not allow/allow other fans to see rsvp result(maybe just number)
- [ ] pin message like telegram
- [ ] post only payed user like facebook post
- [ ] create calendar event on day which selected
- [ ] pull to refresh in organization update chat list
- [ ] show user platform and payment type in admin user profile
- [ ] notification messages




------------------------
- [ ] payment and fund raising
	- [ ] team funded site
	- [ ] my camp payment provider
		- [ ] talk to reza => free with minimum detail with hard limit
	- [ ] mission hill 8 /11
	- [ ] errors in system
	- [ ] document


- [ ] my camp needed
	- [ ] create multiple payment protal link for each person
	- [ ] does links has expire date
	- [ ] webhook to send link with some information of user and organization to our server plus payment portal information(including portal link)
	- [ ] api to get payment portal total balance or transactions with names or webhook to send us all transaction with user informaiton and portal information
	- [ ] create redirect link for IMA user to create portal
Here is a draft outlining the requested features for the collaboration between IMA TEAM and My Camp:

---

**Collaboration Document between IMA TEAM and My Camp**

**Purpose**: This document outlines the key features and integrations that IMA TEAM requires from My Camp, a payment portal provider, to enhance the functionality and payment experience within the IMA TEAM application.

---

### Features Required from My Camp

1. **Creation of Multiple Payment Portal Links**
   - Ability to generate unique payment portal links for each user within IMA TEAM.
   - Each link should be customizable for individual users as needed.

2. **Expiration Date for Payment Links**
   - The generated payment portal links must have an optional expiration date feature to ensure security and control over payment timelines.

3. **Webhook Integration for Payment Link Information**
   - My Camp should provide a webhook service that sends detailed information to IMA TEAM’s server whenever a payment link is created. 
   - The data sent should include:
     - **User Information**: Details about the user for whom the link is created.
     - **Organization Information**: Details of the organization associated with the user.
     - **Payment Portal Information**: Including the generated portal link and any other relevant metadata.

4. **API or Webhook for Transaction and Balance Information**
   - My Camp should offer either:
     - An **API** to retrieve the total balance and detailed transaction history, including transaction amounts and associated user names.
     - Alternatively, a **webhook** that sends all transaction details to IMA TEAM’s server. The webhook should provide:
       - **Transaction Details**: Including transaction amounts, timestamps, and descriptions.
       - **User Information**: Linking transactions to specific users.
       - **Portal Information**: Details about the payment portal used.

5. **Redirect Link for Portal Creation**
   - A mechanism to create a redirect link for IMA TEAM users that takes them directly to the My Camp portal setup page.
   - This should simplify the process of setting up payment portals for users within the IMA TEAM app.

---

Please review and provide feedback or additional requirements to finalize the collaboration terms.

---

Would you like any adjustments or more details added to this draft?



---------------------
- sub/unsub users
- feeds
- personal channel
- home feed
- like comment
- telegram tore

- twiter like
- hastagh



- [ ] delete by another admin
- [ ] hashtag

- [ ] share post as image or gift
	- [ ] create template to put our image 
- [ ] flow for instering reals instagram and short youtube and post in ima as feed
	- [ ] download images and videos to our s3 
	- [ ] extract text and hashtags

-  create
- title
- body
- icon
- data => type sign 
- is_seen
return count of unread messages
filter all - unread -read
type
