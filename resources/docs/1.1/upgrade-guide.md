# Upgrading from 1.0 to 1.1

---

<a name="section-1"></a>

### Database changes
Version 1.1 contains the new `discount_coupons` table. Make sure you have published the migration by running the following command:
```bash
php artisan vendor:publish --provider="Happypixels\Shopr\ShoprServiceProvider" --tag="migrations"
``` 
...or by copying [the migration file](https://github.com/happypixels/laravel-shopr/blob/feature/discount-coupons/database/migrations/create_discount_coupons_table.php.stub) into your project.

### Configuration changes
Make sure you add the following into your `config/shopr.php` configuration file:
```php
'discount_coupons' => [
        
    /**
     * The validation rules for adding a discount coupon to the cart.
     * You may remove or add rules as you'd like, this is simply a common suggestion.
     */
    'validation_rules' => [
        Happypixels\Shopr\Rules\Cart\CartNotEmpty::class,
        Happypixels\Shopr\Rules\Discounts\OnlyOneCouponPerOrder::class,
        Happypixels\Shopr\Rules\Discounts\CouponHasNotBeenApplied::class,
        Happypixels\Shopr\Rules\Discounts\CouponExists::class,
        Happypixels\Shopr\Rules\Discounts\DateIsWithinCouponTimespan::class,
        Happypixels\Shopr\Rules\Discounts\CartValueAboveCouponLimit::class
    ]
],
```