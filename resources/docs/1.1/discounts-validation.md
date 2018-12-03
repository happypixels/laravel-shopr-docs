# Validating a discount coupon

---

<a name="section-1"></a>

When allowing your customers to apply discount coupons to their cart it's important to validate the given coupon code to make sure it's valid and applicable. Shopr comes with a set of default rules to make sure the most common requirements are met:
```php
'discount_coupons' => [
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
These rules are validated when a customer attempts to add a discount coupon to their cart. The default rules make sure the following statements are true:
1. The cart contains shoppable items
2. There are no other discount coupons applied to the cart
3. The desired coupon hasn't already been applied
4. The desired coupon exists in the database
5. The current date and time is within the desired coupon's valid timespan
6. The cart value is higher than the specified limit. If no limit is set on the coupon, the cart value must be higher than the coupon value so the total price doesn't become negative

To add your own rules to this process, create a new rule as described [in the Laravel docs](https://laravel.com/docs/5.7/validation#custom-validation-rules), then add it to the list in your configuration file.
In your new Rule class, you'll have the following method: 
```php
public function passes($attribute, $value)
{
    // Perform your validation
}
```
The `$value` variable is the code the customer has entered.

### Translating the default rule messages
You may wish to translate the messages returned when any of the default rules fail. First, publish the package translation files:
```text
php artisan vendor:publish --provider="Happypixels\Shopr\ShoprServiceProvider" --tag="translations"
```
These will be located in `resources/lang/vendor/shopr`. You can now add your own languages or customize the default (english) messages.