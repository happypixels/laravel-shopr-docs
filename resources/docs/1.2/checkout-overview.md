# Checkout - overview

---

<a name="section-1"></a>

### The checkout process
When the user is satisfied with their shopping cart and are ready to check out, you'll make an ajax request to our `checkout/charge` endpoint, the cart will be converted to an order and an attempt will be made to process the payment. If everything is successful, you'll be returned a redirect url for the order receipt.

### Available payment gateways
We currently support payments through `Stripe` out of the box. However, our payment mechanism is powered by https://github.com/thephpleague/omnipay so any gateway supported there should be fairly easy to implement.
