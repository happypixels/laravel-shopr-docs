# Checkout - paying

---

<a name="section-1"></a>

This page contains general information about the charge request and response. To learn how to implement Stripe specifically, check the [Stripe implementation guide](/{{version}}/gateways/stripe).

| METHOD | URI   |
| :      | :-    |
| POST | `/api/shopr/checkout/charge` |

**Example body**
```text
{
    gateway: 'Stripe', // required
    payment_method_id: paymentMethod.id, // required
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
    "redirect": "https://your-app.com/order-confirmation?token=uniqueOrderToken",
    "token": "uniqueOrderToken"
}
```

**Example error response:**

```text
// Response code: 400
{
    "message": "The payment failed.",
    "reason": "Insufficient funds"
}
```
