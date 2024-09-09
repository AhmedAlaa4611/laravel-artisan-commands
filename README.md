## Laravel Artisan Commands
Comprehensive documentation on Laravel artisan commands.

## Table of Contents
- [Composer](#composer)
- [Artisan](#artisan)
- [Serve](#serve)
- [Migration](#migration)
- [Factory](#factory)
- [Seeders](#seeders)
- [Database](#database)
- [Model](#model)
- [View](#view)
- [Controller](#controller)
- [Route](#route)
- [Middleware](#middleware)
- [Policy](#policy)
- [Tinker](#tinker)
- [Key Generate](#key-generate)
- [Component](#component)
- [Rule](#rule)
- [Request](#request)
- [Command](#command)
- [Schedule](#schedule)
- [Mail](#mail)
- [Notification](#notification)
- [Event](#event)
- [Listener](#listener)
- [Observer](#observer)
- [Tests](#tests)
- [Crud Generator](#crud-generator)
- [Filament](#filament)
- [Links](#links)
- [Threads](#threads)
- [Bat](#bat)
- [Set Up](#set-up)
- [Livewire](#livewire)
- [Running Pint](#running-pint)
- [Terms](#terms)

## Composer
1. Creating a new project:
```sh
composer create-project laravel/laravel app-name
```
2. Find outdated composer dependencies:
```sh
composer outdated
```
3. Updating outdated composer dependencies:
```sh
composer update
```
4. Display all the dependencies in your project:
```sh
composer outdated --all
```
5. Clearing composer cache:
```sh
composer clear-cache
```
6. Updates Composer itself:
```sh
composer self-update
```

## Artisan
- Some artisan commands:
```sh
php artisan
```
```sh
php artisan --help
```
```sh
php artisan --version
```
```sh
php artisan about
```

## Serve
1. Booting up a server:
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
6. Show the status of each migration:
```sh
php artisan migrate:status
```

## Factory
1. To create a factory execute the following artisan command:
```sh
php artisan make:factory PostFactory
```
2. Laravel faker link:
```sh
https://fakerphp.org
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

## Database
1. To show the structure of a specific table.
```sh
php artisan db:table users
```

## Model
1. Creating the model:
```sh
php artisan make:model Product
```
2. Optionally we can create `migration, factory, seeder, and resource controller` for this model:
```sh
php artisan make:model Product -mfsr
```
3. Indicates if the generated model should be a custom intermediate table model `pivot table`:
```sh
php artisan make:model UserProduct -mp
```
4. Finally, we can create them all including the `form request class`:
```sh
php artisan make:model Post --all
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
php artisan make:controller FirstController --resource
```
3. Creating a controller with `CRUD` methods and `Route model binding`:
```sh
php artisan make:controller FirstController --resource --model=Post
```

## Route
1. List all registered routes:
```sh
php artisan route:list
```
2. List all registered routes without vendor ones:
```sh
php artisan route:list --except-vendor
```
3. Remove the route cache file:
```sh
php artisan route:clear
```

## Middleware
1. Creating Middleware:
```sh
php artisan make:middleware CheckPayment
```
2. Registering Middleware in `bootstrap/app.php`:
```php
withMiddleware(function (Middleware $middleware) {
    $middleware->alias([
        'check.payment' => \App\Http\Middleware\CheckPayment::class,
    ]);
})
```

## Policy
1. Creating Policy:
```sh
php artisan make:policy PostPolicy --model=Post
```

## Tinker
1. To execute Laravel code from CMD:
```sh
php artisan tinker
```

## Key Generate
1. Generating a new key on deployment:
```sh
php artisan key:generate
```

## Component
1. How to make a component class:
```sh
php artisan make:component FirstComponent
```

## Rule
1. Defining a new rule:
```sh
php artisan make:rule FirstRule
```

## Request
1. Defining a new request:
```sh
php artisan make:request StoreTaskRequest
```
```sh
php artisan make:request UpdateTaskRequest
```

## Command
1. To make a command in Laravel:
```sh
php artisan make:command FirstCommand
```
2. To run your custom command:
```sh
php artisan app:first-command
```

## Schedule
1. Running the Scheduler Locally:
```sh
php artisan schedule:work
```
- This command will run in the foreground and invoke the scheduler until you terminate the command.

## Mail
1. Creating a mail:
```sh
php artisan make:mail FirstMail --markdown=emails.welcome
```

## Notification
1. Creating a notification:
```sh
php artisan make:notification FirstNotification
```

## Event
1. Creating the event:
```sh
php artisan make:event UserLoggedOut
```

## Listener
1. Creating the listener:
```sh
php artisan make:listener SetUserInactive --event=UserLoggedOut
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
- **Note:** The migration table for the specific resource that you need to make a `CRUD` for it should be created.
1. Installing the ibex package.
```sh
composer require ibex/crud-generator --dev
```
2. Then make `CRUD operations` for the migration table:
```sh
php artisan make:crud posts
```
3. Run npm commands:
```sh
npm install
```
```sh
npm run dev
```
4. Serving the application and use `URL` to request the page of creating the resource, display a list of it, and more.
- **Note:** There are several other packages for doing the same.

## Filament
1. Creating filament resource:
```sh
php artisan make:filament-resource Post --view --generate
```

## Links
```sh
https://laravel.com/docs/11.x
```
```sh
https://livewire.laravel.com
```
```sh
https://filamentphp.com
```
```sh
https://bladewindui.com
```
```sh
https://getbootstrap.com
```
```sh
https://tailwindcss.com
```
```sh
https://daisyui.com
```
- **Note:** `tailwindcss.com` and `daisyui.com` are working together.
```sh
https://tailwindui.com
```
```sh
https://laracasts.com/series/whats-new-in-laravel-5
```
```sh
https://laracasts.com/series/laravel-8-from-scratch
```
- 30 Days to Learn Laravel.
```sh
https://www.youtube.com/watch?v=1NjOWtQ7S2o&list=PL3VM-unCzF8hy47mt9-chowaHNjfkuEVz
```
- Fun with openai and Laravel
```sh
https://laracasts.com/series/fun-with-openai-and-laravel
```
```sh
coding2go    **YouTube and Website**
```
- fake()
```sh
https://fakerphp.org
```

## Threads
1. Example code in cpp `uses threads` to booting up a server to the application and open your browser in a specified `IP address and port number`:
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

## Bat
1. Example code in bat `uses multiple cmd windows` to booting up a server to the application:
```bat
@echo off
start "Starting the el araby center site . . ." cmd /c "php artisan serve"
start "" cmd /c "start http://127.0.0.1:8000"
```

## Set Up
- Set up a Laravel project that you've downloaded from GitHub:
1. Install composer dependencies:
```sh
composer install
```
2. Generate the application key:
```sh
php artisan key:generate
```
3. Install NPM dependencies (optional):
```sh
npm install
npm run dev
```
4. Run migrations:
```sh
php artisan migrate
```
5. Serve the application:
```sh
php artisan serve
```

## Livewire
```sh
https://bootcamp.laravel.com/livewire/installation
```

## Running Pint
1. You can instruct Pint to fix code style issues:
```sh
./vendor/bin/pint
```

## Terms
- Patch or Minor Release.
- Major Release.
- Direct Dependencies.
- Transitive Dependencies.
- Breeze, Jetstream, and Sanctum are Laravel packages used for authentication.
- Choose Breeze if you need simple auth scaffolding, Jetstream if you want a robust application with features like teams and two-factor authentication, and Sanctum if you're building an API or single-page application.
- Laravel Shift is used to upgrade Laravel applications.
- Laravel Sail is a lightweight command-line interface for Laravel that provides a simple and convenient way to set up a local development environment using Docker, Removing the "it works on my machine" problem.
- MariaDB was Created by the original developers of MySQL as a fork of MySQL after the Oracle acquisition to ensure it remains free and open source. The MariaDB Foundation maintains MariaDB.
- SQL is a set of commands for interacting with relational database management systems (RDBMS).
- A symmetric key cryptosystem uses the same key to encrypt and decrypt.
- A public key cryptosystem uses a public key to encrypt and a private key to decrypt.
