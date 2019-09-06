# Custom Order/OrderItem models

---

<a name="section-1"></a>

You may use your own models for managing orders and order items. To do so, start by configuring the `models` section of the configuration file:
```php
'models' => [
    'Order' => App\Order::class,
    'OrderItem' => App\OrderItem::class,
],
```
Your custom models should extend the package's Order and OrderItem models, like so:

```php
use Happypixels\Shopr\Models\Order as ShoprOrder;

class Order extends ShoprOrder 
{

}
```
```php
use Happypixels\Shopr\Models\OrderItem as ShoprOrderItem;

class OrderItem extends ShoprOrderItem 
{

}
```