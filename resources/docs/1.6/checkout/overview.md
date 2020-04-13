# Checkout - overview

---

<a name="section-1"></a>

### The checkout process
When the user is satisfied with their shopping cart and are ready to check out, you'll make an ajax request to our `checkout/charge` endpoint, where an attempt will be made to process the payment. You will then be returned a redirect url which leads to the order receipt if successful, or the payment confirmation page if required.

### Handling payment confirmations
The entire payment confirmation process is handled out of the box. It even renders a nice error page if the confirmation fails. All you need to do is make sure you redirect to the returned url when the `checkout/charge` call is done.

### Available payment gateways
We currently support accepting payments through Stripe out of the box. To learn how to implement it, see the [Stripe guide](/{{version}}/gateways/stripe).
