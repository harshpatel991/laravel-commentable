This is a a fork of v1.0.1. slynova/laravel-commentable since the repo owner has removed it.

As a temporary work around, if your project can't resolve the slynova/laravel-commentable dependency and you are using v1.0.1, you can switch to using this repo as the source:

  1. Add this to your composer.json:
```shell
"repositories": [
    {
        "type": "vcs",
        "url": "https://github.com/harshpatel991/laravel-commentable"
    }
]
```

  2. Change the dependency to point to this repo:
```shell
"harshpatel991/laravel-commentable": "dev-master"
```

  3. Change namespace of the provider
```php
harshpatel991\Commentable\ServiceProvider::class // add this
Slynova\Commentable\ServiceProvider::class // remove this
```

  4. Rename import namespaces from slynova to harshpatel991
```php
use harshpatel991\Commentable\Models\Comment; // add this
use Slynova\Commentable\Models\Comment; // remove this
```

  5. Run composer update on your local machine

  6. Run composer install on your deployment server

# Laravel-Commentable

[![StyleCI](https://styleci.io/repos/45703619/shield)](https://styleci.io/repos/45703619)
[![License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](https://tldrlegal.com/license/mit-license)
[![Total Downloads](https://img.shields.io/packagist/dt/slynova/laravel-commentable.svg?style=flat-square)](https://packagist.org/packages/slynova/laravel-commentable)

[![SensioLabsInsight](https://insight.sensiolabs.com/projects/8d9f7ba6-6801-486f-aa04-570855860d57/big.png)](https://insight.sensiolabs.com/projects/8d9f7ba6-6801-486f-aa04-570855860d57)

Laravel Commentable adds polymorphic threaded comments to Laravel 5.1 and above.

This package use Nested Set pattern with [Baum](https://github.com/etrepat/baum).<br>
[More information about Nested Set](http://en.wikipedia.org/wiki/Nested_set_model)

# Table of Contents

* [Requirements](#requirements)
* [Getting Started](#getting-started)
* [Example](#example)
* [Change Logs](#change-logs)
* [Contribution Guidelines](#contribution-guidelines)

# <a name="requirements"></a>Requirements

* As Laravel 5.1 require PHP 5.5.9+, we required the same version.

# <a name="getting-started"></a>Getting Started

1. Require the package with [Composer](https://getcomposer.org).
    ```shell
    $ composer require slynova/laravel-commentable
    ```

2. Add the package to your application service providers in `config/app.php`.
    ```php
    'providers' => [

        Illuminate\Foundation\Providers\ArtisanServiceProvider::class,
        Illuminate\Auth\AuthServiceProvider::class,
        ...
        Slynova\Commentable\ServiceProvider::class,

    ],
    ```

3. Publish the package's migrations to your application and migrate.
    ```shell
    $ php artisan vendor:publish --provider="Slynova\Commentable\ServiceProvider" --tag="migrations"
    $ php artisan migrate
    ```

# <a name="example"></a>Example

You can find an usage example of this package in the [laravel-commentable-example](https://github.com/Slynova-Org/laravel-commentable-example) repository.

# <a name="change-logs"></a>Change Logs

Nothing has been changed from the first release.

# <a name="contribution-guidelines"></a>Contribution Guidelines

Support follows PSR-2 PHP coding standards, and semantic versioning.

Please report any issue you find in the issues page.
Pull requests are welcome.
