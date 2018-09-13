# Checkout - paying

---

<a name="section-1"></a>

Before you make the charge request, you may need a gateway specific implementation.  
For example, if you're using `Stripe`, you may want to use their modal for entering card details. When done, you'll receive a token from `Stripe` which you'll pass along to our charge endpoint.

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
