# Installation & setup

---

<a name="section-1"></a>

Install Laravel Shopr via Composer:
```bash
composer require happypixels/laravel-shopr
```
*The package will automatically register it's service provider.*  
<br>
Publish and run the migrations:
```bash
php artisan vendor:publish --provider="Happypixels\Shopr\ShoprServiceProvider" --tag="migrations"
php artisan migrate
```
<br>
Publish and review the config file:
```bash
php artisan vendor:publish --provider="Happypixels\Shopr\ShoprServiceProvider" --tag="config"
```
*In this file you can modify your preferred currency, tax, default templates, email triggers and so on.*

You may publish the package views if you wish to modify them:
```bash
php artisan vendor:publish --provider="Happypixels\Shopr\ShoprServiceProvider" --tag="views"
```
<br>
Optionally you may publish the translation files to make them modifiable:
```bash
php artisan vendor:publish --provider="Happypixels\Shopr\ShoprServiceProvider" --tag="translations"
```
