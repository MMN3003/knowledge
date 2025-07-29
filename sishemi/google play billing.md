For each product, you need to provide a unique product ID, a title, a description, and pricing information. Subscriptions have additional required information, such as selecting whether it's an auto-renewing or prepaid renewal type for the base plan.

### Indicate a personalized price

If your app can be distributed to users in the European Union, use the `setIsOfferPersonalized()` method when calling `launchBillingFlow` to disclose to users that an item's price was personalized using automated decision-making.