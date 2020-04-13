# Upgrading from v1 to v2

---

<a name="section-1"></a>

Version 2 introduces a few breaking changes if you're currently using version 1:

### Code changes you likely need to make
**Laravel support**  
Version 2 drops support for Laravel versions prior to 5.8. If you're on 5.7 or lower, stick to version 1.

**The REST API checkout endpoint**  
The URL for the checkout endpoint in the REST API has changed from `/api/shopr/checkout/charge` to `/api/shopr/cart/checkout`.

**The config file**  
Changes have been made to the config file. You may either republish it (see Installation & setup), or add the following content to it:
```php
/**
 * Available values: gross, net.
 * When net is selected, tax will be added to the price.
 * When gross is selected, tax is included in the price.
 */
'tax_mode' => 'gross',

/**
 * Configuration options for the optional REST API.
 */
'rest_api' => [
    'enabled' => true,
    'prefix' => 'api/shopr',
    'middleware' => [
        // YourCustomMiddleware::class
    ],
],
```
More details about the configuration file can be found on the Configuration page.

### Conceptual changes
**Cart item prices**  
The unit price of an item now includes any sub items added to that item.

**Order payment status**  
Orders that haven't had their payments confirmed yet get the payment_status `pending_confirmation` rather than `paid`. No confirmation emails are sent until the payment has been confirmed.

### Internal API changes (likely won't affect your site)
-The `getAllItems()` method on `Happypixels\Shopr\Cart\Cart` has been renamed to `all()`.  
-The `$subItems` property on `Happypixels\Shopr\Cart\CartItem` has been renamed to `$sub_items`.  
-The `$total` property on  `Happypixels\Shopr\Cart\CartItem` has been renamed too `$total_price`.
