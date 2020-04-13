# Applying a discount coupon

---

<a name="section-1"></a>

Discount coupons are basically Shoppables with a negative price. However, you can't add a discount coupon the way you add a regular item to the cart. Instead, use the endpoint described below. Applying a discount coupon will return the full cart summary.

| METHOD | URI   |
| :      | :-    |
| POST | `/api/shopr/cart/discounts` |

**Example body**
```text
{
    code: 'HALFPRICE' // required
}
```

**Example response:**
```text
{
    "items": [{
        "id": "111111111111",
        "quantity": 1,
        "shoppableType": "App\\Models\\Camera",
        "shoppableId": 1,
        "shoppable": {
            "id": 1,
            "title": "The best camera",
            "price": 100,
            "price_formatted": "$100,00"
        },
        "options": {
            "color": "Silver",
        },
        "subItems": [],
        "total": 100,
        "price": 100,
        "price_formatted": "$100,00"
    }],
    "discounts": [{
        "id": "222222222222",
        "quantity": 1,
        "shoppableType": "Happypixels\\Shopr\\Models\\DiscountCoupon",
        "shoppableId": 1,
        "shoppable": {
            "id": 1,
            "valid_from": "2018-01-01 12:00:00",
            "valid_until": "2020-12-31 12:00:00",
            "uses": 1,
            "code": "HALFPRICE",
            "description": "",
            "is_fixed": 0,
            "value": "50.00",
            "created_at": "2018-01-01 10:00:00",
            "updated_at": "2018-01-01 10:00:00",
            "deleted_at": null
        },
        "options": [],
        "subItems": [],
        "total": -50,
        "price": -50,
        "price_formatted": "$−50,00"
    }],
    "sub_total": 50,
    "sub_total_formatted": "$50,00",
    "tax_total": 0,
    "tax_total_formatted": "$0,00",
    "total": 50,
    "total_formatted": "$50,00",
    "count": 1
}
```