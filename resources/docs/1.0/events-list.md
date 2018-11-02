# Events

---

<a name="section-1"></a>

### Overview
Sometimes you may want to run custom logics when various shop actions are performed. For this reason, Shopr will fire events when these actions are executed. You may listen to the events that are relevant for your project and do what you wish when they're fired.

Here's an example event listener:
```php
use Illuminate\Support\Facades\Event;

Event::listen('shopr.order.created', function ($order) {
    // Do something.
});
```

### Full list of events

**shopr.orders.created**  
Fired when an order is successfully created. Passes the `Happypixels\Shopr\Models\Order` object to your listener.

**shopr.cart.items.created**  
Fired when an item is added to the cart. Passes the `Happypixels\Shopr\CartItem` object to your listener.

**shopr.cart.items.updated**  
Fired when an item is updated in the cart. Passes the `Happypixels\Shopr\CartItem` object to your listener.

**shopr.cart.items.deleted**  
Fired when an item is deleted in the cart. Passes the `Happypixels\Shopr\CartItem` object to your listener.