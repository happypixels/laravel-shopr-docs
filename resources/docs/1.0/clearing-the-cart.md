# Clearing the cart

---

<a name="section-1"></a>

Clearing the cart will return the full cart summary.

| METHOD | URI   |
| :      | :-    |
| DELETE | `/api/shopr/cart` |
  
**Example response:**

```text
{
	"items": [],
	"sub_total": 0,
	"sub_total_formatted": "$0,00",
	"tax_total": 0,
	"tax_total_formatted": "$0,00",
	"total": 0,
	"total_formatted": "$0,00",
	"count": 0
}
```
