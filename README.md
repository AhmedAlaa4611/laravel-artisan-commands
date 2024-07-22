## Laravel Artisan Commands
Comprehensive documentation on Laravel artisan commands.

## Table of Contents
- [Composer](#composer)
- [Serve](#serve)
- [Migration](#migration)
- [Observer](#observer)
- [Tests](#tests)

## Composer
1. Creating a new project:
```sh
composer create-project laravel/laravel app-name
```
2. Clearing composer cache:
```sh
composer clear-cache
```
3. Updating composer:
```sh
composer self-update
```

## Serve
1. Serving the application:
```sh
php artisan serve
```
2. By default this will serve your application in `localhost:8000` to change the port:
```sh
php artisan serve --port=8080
```

## Migration
1. To migrate the database:
```sh
php artisan migrate
```
2. To rollback the migration:
```sh
php artisan migrate:rollback
```
3. To fresh your database:
```sh
php artisan migrate:fresh
```
4. To fresh your database and running seeders:
```sh
php artisan migrate:fresh --seed
```

## Observer
1. If you are listening for many events on a given model, you may use observers to group all of your listeners into a single class:
```sh
php artisan make:observer UserObserver --model=User
```
2. To `register an observer`, you may place the ObservedBy attribute on the corresponding model:
```php
<?PHP

namespace App\Models;

use App\Observers\UserObserver;
use Illuminate\Database\Eloquent\Attributes\ObservedBy;
use Illuminate\Foundation\Auth\User as Authenticatable;
 
#[ObservedBy([UserObserver::class])]
class User extends Authenticatable
{
    //
}
```

## Tests
1. To create a new test case, use the `make:test` Artisan command. By default, tests will be placed in the `tests/Feature` directory:
```sh
php artisan make:test UserTest
```
2. Running tests:
```sh
php artisan test
```
4. Some arguments that can be passed to the Artisan test command:
```sh
php artisan test --testsuite=Feature --stop-on-failure
```
4. The Artisan test runner also includes a convenient mechanism for listing your application's slowest tests:
```sh
php artisan test --profile
```
