# Upgrading from 1.4 to 1.5

---

<a name="section-1"></a>

> {primary} This release adds support for Strong Customer Authentication (SCA) and 3D Secure authentication for payments by leveraging the Stripe Payment Intents API.
It contains a few breaking changes so be sure to read through this guide carefully!

### The `shopr.orders.created` event
If you listen to the `shopr.orders.created` event to find out when an order has been successfully paid, you should instead listen to the new `shopr.orders.confirmed` event. The reason for this is that the new SCA payment flow sometimes require an additional confirmation, and if that fails the payment does not succeed. However, the order has already been created. The `shopr.orders.confirmed` event is only fired when an order is successfully paid.

### The new SCA compatible payment flow
The new Payment Intents API requires some modification to your frontend. It's not much, but it will make payments fail if you don't upgrade. Make sure you follow the [step by step guide](/1.5/gateways/stripe#accepting-payments-with-stripe) to set it up correctly.
