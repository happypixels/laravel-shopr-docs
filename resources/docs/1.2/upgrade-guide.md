# Upgrading from 1.1 to 1.2

---

<a name="section-1"></a>

### Configuration changes (optional)
You may add the `models` key to your `config/shopr` configuration file:
```php
/*
 * The database models. You may swap these with your own models, just make sure they extend the
 * corresponding package model rather than the standard Eloquent model.
 */
'models' => [
    'Order' => Happypixels\Shopr\Models\Order::class,
    'OrderItem' => Happypixels\Shopr\Models\OrderItem::class,
],
``` 
However, this isn't necessary if you don't intend on using your own order models.