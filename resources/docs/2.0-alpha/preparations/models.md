# Making your models shoppable

---

<a name="section-1"></a>

Before you can let the user add a model to the cart and eventually convert it into an order, you need to make it shoppable. To make a model shoppable, simply extend the custom `Shoppable`  class rather than the `Model` class:

```php
use Happypixels\Shopr\Models\Shoppable;

class Product extends Shoppable {

}
```

### Customizing the default attributes
All shoppable models need to provide their id, title and price for the Cart and Order management to be correct. The `Shoppable` class has a few defaults that you are free to override if needed:

```php
/**
 * The identifier of the model.
 *
 * @return mixed
 */
public function getId()
{
    return $this->id;
}

/**
 * The name/title of the model.
 *
 * @return string
 */
public function getTitle()
{
    return $this->title;
}

/**
 * The price of the model.
 *
 * @return mixed
 */
public function getPrice()
{
    return $this->price;
}
```
