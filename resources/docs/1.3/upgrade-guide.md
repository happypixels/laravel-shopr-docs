# Upgrading from 1.1 to 1.2

---

<a name="section-1"></a>

### Configuration changes (optional)
You may add the `money_formatter` key to your `config/shopr` configuration file:
```php
/*
 * The money formatter class. You may provide your own class here, just make sure it extends
 * the default Happypixels\Shopr\Money\Formatter class.
 */
'money_formatter' => Happypixels\Shopr\Money\Formatter::class,
``` 
However, this isn't necessary if you don't plan on using your own formatter.