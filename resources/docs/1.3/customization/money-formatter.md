# Custom Money Formatter

---

- [Setup](#setup)
- [Available options](#options)
- [Formatting with more freedom](#free-formatting)

<a name="setup"></a>
### Setup
You may use your own money formatter. To do so, configure the `money_formatter` key of the configuration file:
```php
'money_formatter' => App\MyFormatter::class,
```
Your formatter should extend the package's Formatter-class, like so:

```php
namespace App;

use Happypixels\Shopr\Money\Formatter;

class MyFormatter extends Formatter 
{

}
```

<a name="options"></a>
### Available options
Now that you have your own formatter set up, you may configure any or all of the following 5 options:
```php
class MyFormatter extends Formatter 
{
    // Which symbol to use when displaying formatted amounts.
    public $symbol = '$';

    // Which side of the amount the symbol should be placed at.
    // Can be either 'before' or 'after'.
    public $symbolPosition = 'before'; 

    // The symbol used as thousand separator.
    public $thousandSeparator = ',';

    // The symbol used for indicating the decimal place.
    public $decimalSeparator = '.';

    // The amount of decimals to enforce. 
    // Note that this will round the amount when defined.
    public $decimalCount = 2;
}
```
> {info} If you leave out any or all of these options, the defaults based on the app locale and configured currency will be used.

<a name="free-formatting"></a>
### Formatting with more freedom
If you don't want to be bound by the options mentioned above, you may instead define a `format`-method on your formatter:
```php
class MyFormatter extends Formatter 
{
    public function format($amount)
    {
        if ($amount > 1000) {
            return 'Server error, too much money.';
        }

        return '$'.$amount;
    }
}
```