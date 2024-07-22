## Laravel artisan commands
Comprehensive documentation on Laravel artisan commands.

## Table of Contents
- [Observer](#observer)
- [Tests](#tests)

## Observer
1. If you are listening for many events on a given model, you may use observers to group all of your listeners into a single class:
```sh
php artisan make:observer UserObserver --model=User
```
2. To `register an observer`, you may place the ObservedBy attribute on the corresponding model:
```sh
<?PHP

namespace App\Models;

use App\Observers\UserObserver;
use Illuminate\Database\Eloquent\Attributes\ObservedBy;
 
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
2. Some arguments that can be passed to the Artisan test command:
```sh
php artisan test --testsuite=Feature --stop-on-failure
```
3. The Artisan test runner also includes a convenient mechanism for listing your application's slowest tests:
```sh
php artisan test --profile
```
