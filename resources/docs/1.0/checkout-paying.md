# Checkout - paying

---
- [Implementing Stripe](/{{version}}/checkout-paying#gateway-stripe)

<a name="section-1"></a>

Before you make the charge request, you may need a gateway specific implementation in between. You can read more about how to implement each gateway further down.

| METHOD | URI   |
| :      | :-    |
| POST | `/api/shopr/checkout/charge` |

**Example body**
```text
{
    gateway: 'Stripe', // required
    token: token.id, // when using Stripe, the token is required to charge the customer
    email: 'test@example.org', // required
    first_name: 'Boaty', // required
    last_name: 'McBoatface', // required
    phone: '(1) 111222333',
    address: 'Boatstreet 1',
    zipcode: '111 22',
    city: 'Boat City',
    country: 'Boatland'
}
```

**Example response:**

```text
{
    "redirect": "https://your-app.com/order-confirmation?token=uniqueOrderToken"
}
```

**Example error response:**

```text
// Response code: 400
{
    "message": "Unable to process your order."
}
```

### Gateway specific implementations

##### Stripe
<a name="gateway-stripe"></a>
When using `Stripe` to process purchases, you first need to open their [Checkout component](https://stripe.com/checkout) to let the user enter their card details and confirm the purchase. When done, you will receive a token which should be included in your request to the `/api/shopr/checkout/charge` endpoint as the `token` parameter.  
If you're using Vue, we highly recommend using [this wrapper component for Stripe Checkout](https://github.com/jofftiquez/vue-stripe-checkout). You can also check out [the demo implementation](https://github.com/happypixels/laravel-shopr-demo/blob/master/resources/js/components/PaymentOptions/Stripe.vue).
