## Laravel Artisan Commands
Comprehensive documentation on Laravel artisan commands.

## Table of Contents
- [Composer](#composer)
- [Serve](#serve)
- [Migration](#migration)
- [Seeders](#seeders)
- [Model](#model)
- [View](#view)
- [Controller](#controller)
- [Route](#route)
- [Tinker](#tinker)
- [Observer](#observer)
- [Tests](#tests)
- [Crud Generator](#crud-generator)
- [Threads](#threads)

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
1. Creating a migration:
```sh
php artisan make:migration create_posts_table
```
2. To migrate the database:
```sh
php artisan migrate
```
3. To rollback the migration:
```sh
php artisan migrate:rollback
```
4. To fresh your database:
```sh
php artisan migrate:fresh
```
5. To fresh your database and running seeders:
```sh
php artisan migrate:fresh --seed
```

## Seeders
1. Creating database seeder:
```sh
php artisan make:seeder FirstSeeder
```
2. Running the seeder:
```sh
php artisan db:seed
```

## Model
1. Creating the model:
```sh
php artisan make:model Product
```
2. Optionally we can create `migration, factory, and seeder` for this model:
```sh
php artisan make:model Product -mfs
```

## View
1. Clearing the cached views:
```sh
php artisan view:clear
```
2. Compiling `blade` views and caching it:
```sh
php artisan view:cache
```

## Controller
1. Creating an empty controller:
```sh
php artisan make:controller FirstController
```
2. Creating a controller with `CRUD` methods:
```sh
php artisan make:controller ProductController --resource
```
3. Creating a controller with `CRUD` methods and `Route model binding`:
```sh
php artisan make:controller ProductController --resource --model=Product
```

## Route
1. List all registered routes:
```sh
php artisan route:list
```
2. Remove the route cache file:
```sh
php artisan route:clear
```

## Tinker
1. To execute Laravel code from CMD:
```sh
php artisan tinker
```

## Observer
1. If you are listening for many events on a given model, you may use observers to group all of your listeners into a single class:
```sh
php artisan make:observer UserObserver --model=User
```
2. To `register an observer`, you may place the ObservedBy attribute on the corresponding model:
```php
#[ObservedBy([UserObserver::class])]
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
3. Some arguments that can be passed to the Artisan test command:
```sh
php artisan test --testsuite=Feature --stop-on-failure
```
4. The Artisan test runner also includes a convenient mechanism for listing your application's slowest tests:
```sh
php artisan test --profile
```

## Crud Generator
1. first create the migration table and run the migration.
2. Installing the ibex package.
```sh
composer require ibex/crud-generator --dev
```
3. Then make `CRUD operations` for the migration table:
```sh
php artisan make:crud posts
```
4. Run npm commands:
```sh
npm install
```
```sh
npm run dev
```

## Threads
1. Example code in cpp `uses threads` to serve your application and open your browser in a specified `IP address and port number`:
```cpp
#include <iostream>
#include <thread>
using namespace std;

void open_app()
{
    system("php artisan serve");
}

void open_browser()
{
    system("start http://localhost:8000");
}

int main()
{
    thread thread_open_app = thread(open_app);
    thread thread_open_browser = thread(open_browser);
    thread_open_app.join();
    thread_open_browser.join();
    return 0;
}
```
