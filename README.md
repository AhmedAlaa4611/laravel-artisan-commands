## Laravel artisan commands
Comprehensive documentation on Laravel artisan commands.

## Table of Contents
- [Tests](#tests)

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
