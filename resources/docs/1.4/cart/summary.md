# Retrieving cart details

---

<a name="section-1"></a>

The cart summary will return the items added to the cart, any applied discount coupons, the total price, calculated tax and similar data.

| METHOD | URI   |
| :      | :-    |
| GET | `/api/shopr/cart` |
  
**Example response:**

```text
{
	"items": [{
		"id": "111111111111",
		"quantity": 1,
		"shoppableType": "App\\Models\\Product",
		"shoppableId": 1,
		"shoppable": {
			"id": 1,
			"title": "An awesome product",
			"price": 10,
			"price_formatted": "$10,00"
		},
		"options": {},
		"subItems": [],
		"total": 10,
		"price": 10,
		"price_formatted": "$10,00"
	}],
	"discounts": [],
	"sub_total": 10,
	"sub_total_formatted": "$10",
	"tax_total": 0,
	"tax_total_formatted": "$0,00",
	"total": 10,
	"total_formatted": "$10",
	"count": 1
}
```

<a name="section-2"></a>
### Only retrieving the cart count

In some cases you may wish to only get the quantity of all items added to the cart. This is also possible:

| METHOD | URI   |
| :      | :-    |
| GET | `/api/shopr/cart/count` |

**Example response:**

```text
{
    "count": 1
}
```
