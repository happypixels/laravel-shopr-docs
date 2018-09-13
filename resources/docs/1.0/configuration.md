# Configuration

---

<a name="section-1"></a>

We'll now go through the configuration file in detail. Some values need to be configured for everything to work properly, so don't skip this step.

### Templates
```php
'templates' => [
    'cart'               => '',
    'checkout'           => '',
    'order-confirmation' => '',
],
```
The template paths for the default views usually needed in a webshop. Defined the way you'd usually define a view path, such as `path.to.my.view`. If left empty, that route will not be registered.  
The `order-confirmation` route will have access to an `$order` variable, to make it easy for you to display the necessary order information.

### Currency
```php
'currency' => 'USD',
```
The currency defines how money will be formatted. Formatted money values will be returned as `attribute_formatted`, such as `$order->total_formatted`.  
The currency must be defined using the ISO4217 format, see https://www.xe.com/iso4217.php for more information and a full currency list.

### Tax
```php
'tax' => 0,
```
This defines the tax percentage which will be calculated on all shoppable items.

### Emails
```php
'admin_emails' => [],

'mail' => [
    'customer' => [
        'order_placed' => ['enabled' => true, 'template' => null, 'subject' => null],
    ],
    'admins' => [
        'order_placed' => ['enabled' => true, 'template' => null, 'subject' => null],
    ],
],
```
The `admin_emails` holds an array of email addresses to the administrators of the site.

The `mail` setting configures various automated emails. For example, when an order is placed you may want to send an email both to the customer and to the administrators.
You may define a custom template in the usual view path format (`path.to.view`). These views will have access to the `$order` variable. However, default templates are used as fallback. You may also define a specific subject if you'd like. 

### Payment gateways
```php
'gateways' => [
    'stripe' => [
        'publishable_key' => env('STRIPE_PUBLISHABLE_KEY', ''),
        'api_key'         => env('STRIPE_SECRET_KEY', '')
    ]
]
```
This setting holds the details about the payment gateways you wish to enable. We currently support `Stripe` out of the box.
