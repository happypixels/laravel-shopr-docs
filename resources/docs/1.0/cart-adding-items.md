# Adding items to the cart

---

<a name="section-1"></a>

Adding items to the cart will return the full cart summary. You can add sub items in order to combine different shoppables.

| METHOD | URI   |
| :      | :-    |
| POST | `/api/shopr/cart/items` |

**Example body**
```text
{
    shoppable_type: 'App\\Models\\Camera', // required
    shoppable_id: 1, // required
    quantity: 1,
    options: {
        color: 'Silver',
    },
    sub_items: [{
        shoppable_type: 'App\\Models\\Lens', // required when providing a sub item
        shoppable_id: 1, // required when providing a sub item
        options: {
            color: 'Space grey'
        }
    }]
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
		"subItems": [{
            "shoppableType": "App\\Models\\Lens",
		    "shoppableId": 1,
            "options": {
                "color": "Space grey"
            }
        }],
		"total": 199,
		"price": 199,
		"price_formatted": "$199,00"
	}],
	"sub_total": 199,
	"sub_total_formatted": "$199,00",
	"tax_total": 0,
	"tax_total_formatted": "$0,00",
	"total": 199,
	"total_formatted": "$199,00",
	"count": 1
}
```

### Price calculations
When adding an item, the price of the main shoppable will be combined with the prices of any sub item shoppables. You may override the main shoppable price by providing a `price` attribute on the request body. For example, you may have an option that costs more or less than the default price.

### Options
The options you provide are completely free. You can append any key-value pairs you'd like.

### Quantity
The quantity will default to 1 unless you provide a different value. If you add an item that's identical to an item that already exists in the cart, the quantity will instead be incremented on that one. Identifying identical items takes options and sub items into account.

### Sub items
Sub items follow the same structure as the main item. You must provide a shoppable id and class namespace, but you may also provide options and quantity if you'd like.
