# Adding items to the cart

---

<a name="section-1"></a>

Removing an item will return the full cart summary.

| METHOD | URI   |
| :      | :-    |
| DELETE | `/api/shopr/cart/items/{id}` |
  
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
	"sub_total": 10,
	"sub_total_formatted": "$10",
	"tax_total": 0,
	"tax_total_formatted": "$0,00",
	"total": 10,
	"total_formatted": "$10",
	"count": 1
}
```
