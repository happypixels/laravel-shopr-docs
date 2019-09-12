# Updating items in the cart

---

<a name="section-1"></a>

When you've added an item to the cart, you may wish to update the quantity. Doing so will return the full cart summary.

| METHOD | URI   |
| :      | :-    |
| PATCH  | `/api/shopr/cart/items/{id}` |

**Example body**
```text
{
    quantity: 2
}
```

**Example response:**

```text
{
	"items": [{
		"id": "111111111111",
		"quantity": 2,
		"shoppableType": "App\\Models\\Product",
		"shoppableId": 1,
		"shoppable": {
			"id": 1,
			"title": "An awesome product",
			"price": 10,
			"price_formatted": "$10,00"
		},
		"subItems": [],
		"total": 20,
		"price": 10,
		"price_formatted": "$10,00"
	}],
	"discounts": [],
	"sub_total": 20,
	"sub_total_formatted": "$20,00",
	"tax_total": 0,
	"tax_total_formatted": "$0,00",
	"total": 20,
	"total_formatted": "$20,00",
	"count": 2
}
```
