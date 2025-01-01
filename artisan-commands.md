## Laravel Artisan Commands
> Comprehensive :100: documentation on Laravel artisan commands :partying_face:.

## Table of Contents
- [Composer](#composer)
- [Artisan](#artisan)
- [Booting up The Application](#booting-up-the-application)
- [Migration](#migration)
- [Factory](#factory)
- [Seeders](#seeders)
- [Database](#database)
- [Model](#model)
- [View](#view)
- [Controller](#controller)
- [Middleware](#middleware)
- [Route](#route)
- [Policy](#policy)
- [Component](#component)
- [Rule](#rule)
- [Request](#request)
- [Command](#command)
- [Schedule](#schedule)
- [Mail](#mail)
- [Notification](#notification)
- [Events and Listeners](#events-and-listeners)
- [Observer](#observer)
- [Tests](#tests)
- [Static Analysis](#static-analysis)
- [Key Generate](#key-generate)
- [Tinker](#tinker)
- [Set Up](#set-up)
- [Crud Generator](#crud-generator)
- [Links](#links)
- [Threads](#threads)
- [Bat](#bat)

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
7. Autoload:
```sh
composer dump-autoload
```
8. Version:
```sh
composer --version
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
```sh
php artisan about --only=cache
```

## Booting up The Application
1. Booting up a server:
```sh
php artisan serve
```
2. By default, this will serve your application in `localhost:8000`. to change the port:
```sh
php artisan serve --port=8080
```

## Migration
1. Creating database migration:
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
7. To dump your migrations to a raw sql:
```sh
php artisan schema:dump
```

## Factory
1. Creating database factory:
```sh
php artisan make:factory PostFactory
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
3. To indicates that the generated model should be a custom intermediate table model `pivot table`:
```sh
php artisan make:model UserProduct -mp
```
4. Finally, we can create them all including the `form request classes`:
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
4. Creating a controller with `CRUD` methods, `Route model binding`, and `Form Requests`:
```sh
php artisan make:controller FirstController --resource --model=Post --requests
```

## Middleware
1. Creating Middleware:
```sh
php artisan make:middleware CheckPayment
```

## Route
1. List all registered routes:
```sh
php artisan route:list
```
2. List all registered routes by definition:
```sh
php artisan route:list --sort=definition
```
3. List all registered routes without vendor ones:
```sh
php artisan route:list --except-vendor
```
4. To generate a route cache:
```sh
php artisan route:cache
```
5. Remove the route cache file:
```sh
php artisan route:clear
```

## Policy
1. Creating Policy:
```sh
php artisan make:policy PostPolicy --model=Post
```

## Component
1. Creating a component class:
```sh
php artisan make:component FirstComponent
```
> You will find the `FirstComponent` class in the `app\View\Components` directory and the `first-component.blade.php` file in the `resources\views\components` directory.

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
> This command will run in the foreground and invoke the scheduler until you terminate the command, so this will not work in production. instead, you need something called `Cron Jobs`.

## Mail
1. Creating a mail:
```sh
php artisan make:mail FirstMail --markdown=emails.welcome
```
> You will find the `FirstMail` class in the `app\Mail` directory and the `welcome.blade.php` file in the `resources\views\emails` directory.

## Notification
1. Creating a notification:
```sh
php artisan make:notification FirstNotification
```

## Events and Listeners
1. Creating an event:
```sh
php artisan make:event UserLoggedOut
```
2. Creating a listener for that event:
```sh
php artisan make:listener SetUserInactive --event=UserLoggedOut
```

## Observer
1. If you are listening for many events on a given model, you may use observers to group all of your listeners into a single class:
```sh
php artisan make:observer UserObserver --model=User
```
2. To `register that observer`, you may place the `ObservedBy` attribute on the corresponding model:
```php
#[ObservedBy([UserObserver::class])]
```

## Tests
1. To create a new test case, use the `make:test` Artisan command:
```sh
php artisan make:test UserTest
```
> By default, tests will be placed in the `tests/Feature` directory.
2. Running tests:
```sh
php artisan test
```
3. To run a specific test class:
```sh
php artisan test --filter=YouTubeManagerTest
```
4. Some arguments that can be passed to the Artisan test command:
```sh
php artisan test --testsuite=Feature --stop-on-failure
```
5. Listing the application's top 10 slowest tests:
```sh
php artisan test --profile
```

## Static Analysis
1. You can instruct Pint to fix code style issues:
```sh
./vendor/bin/pint
```

## Key Generate
1. Generating a new key on deployment:
```sh
php artisan key:generate
```

## Tinker
1. To execute Laravel code from CMD:
```sh
php artisan tinker
```

## Set Up
> Set up a Laravel project that you've downloaded from GitHub:
1. Install composer dependencies:
```sh
composer install
```
> Copy the content of `.env.example` to a new file called `.env`.
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

## Crud Generator
> First create the migration table.
1. Installing the `ibex` package.
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
4. Booting up the application and use `URL` to request the page of creating the resource, display a list of it, and more.
> There are several other packages for doing the same.

## Links
```sh
https://laravel.com/docs/11.x
```
```sh
https://livewire.laravel.com
```
```sh
https://bootcamp.laravel.com/livewire/installation
```
```sh
https://laravel-notification-channels.com/telegram
```
```sh
https://laravel-news.com
```
```sh
https://blog.laravel.com
```
```sh
https://developer.mozilla.org/en-US/docs/Web/HTTP
```
```sh
https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API
```
```sh
https://codelabs.developers.google.com/codelabs/webrtc-web/#0
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
```sh
https://bladewindui.com
```
> `tailwindcss.com` and `daisyui.com` are working together.
```sh
https://laracasts.com/series/whats-new-in-laravel-5
```
```sh
https://laracasts.com/series/laravel-8-from-scratch
```
```sh
https://laracasts.com/series/fun-with-openai-and-laravel
```
> Learn Laravel in 30 Days.
```sh
https://www.youtube.com/playlist?list=PL3VM-unCzF8hy47mt9-chowaHNjfkuEVz
```
```sh
https://coding2go.com
```
```sh
https://www.youtube.com/@coding2go
```
```sh
https://fakerphp.org
```
```sh
https://phpunit.de/index.html
```

## Threads
1. Example code in cpp `uses threads` for booting up a server to the application and open your browser in a specified `IP address and port number`:

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
1. Example code in bat `uses multiple CMD windows` for booting up a server to the application:
```bat
@echo off
start "Starting the el araby center site . . ." cmd /c "php artisan serve"
start "" cmd /c "start http://127.0.0.1:8000"
```