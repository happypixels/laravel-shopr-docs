# Installation & setup

---

<a name="section-1"></a>

Install Laravel Shopr via Composer:
```text
composer require happypixels/laravel-shopr
```
*The package will automatically register its service provider.*

Publish and run the migrations:
```text
php artisan vendor:publish --provider="Happypixels\Shopr\ShoprServiceProvider" --tag="migrations"
php artisan migrate
```

Publish and review the config file:
```text
php artisan vendor:publish --provider="Happypixels\Shopr\ShoprServiceProvider" --tag="config"
```
*In this file you can modify your preferred currency, tax, default templates, email triggers and so on.*
