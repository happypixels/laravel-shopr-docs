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

**shopr.cart.cleared**  
Fired when the cart is cleared. Passes nothing to your listener.

**shopr.cart.items.added**  
Fired when a new item is added to the cart. Passes the `Happypixels\Shopr\CartItem` object to your listener.

**shopr.cart.items.updated**  
Fired when an item is updated in the cart or when you add an item that already exists in the cart. Passes the updated `Happypixels\Shopr\CartItem` object to your listener.

**shopr.cart.items.deleted**  
Fired when an item is deleted in the cart. Passes the `Happypixels\Shopr\CartItem` object to your listener.

**shopr.cart.discounts.added**  
Fired when a discount coupon is added to the cart. Passes the `Happypixels\Shopr\CartItem` object representing the discount coupon to your listener.