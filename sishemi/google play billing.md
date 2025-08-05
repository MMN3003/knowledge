For each product, you need to provide a unique product ID, a title, a description, and pricing information. Subscriptions have additional required information, such as selecting whether it's an auto-renewing or prepaid renewal type for the base plan.

### Indicate a personalized price

If your app can be distributed to users in the European Union, use the `setIsOfferPersonalized()` method when calling `launchBillingFlow` to disclose to users that an item's price was personalized using automated decision-making.

### Verify the purchase

Your app should always verify the legitimacy of purchases before granting benefits to a user. This can be done by following the guidelines described in [Verify purchases before granting entitlements](https://developer.android.com/google/play/billing/security?_gl=1*ees1it*_up*MQ..*_ga*MTg1MTQyMTQyLjE3NTM3ODUzNDQ.*_ga_6HH9YJMN9M*czE3NTM3ODUzNDMkbzEkZzAkdDE3NTM3ODU3MTAkajYwJGwwJGg2OTE3NzIxNA..#verify). Only after verifying the purchase should your app continue to process the purchase and grant entitlements to the user, which is discussed in the next section.\





previews leader id in team
and auto join after accept 
api transfer request by id return teams
