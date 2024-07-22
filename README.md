## Laravel artisan commands
Comprehensive documentation on Laravel artisan commands.

## Table of Contents
- [Tests](#tests)

## Tests
Creating Tests
To create a new test case, use the make:test Artisan command. By default, tests will be placed in the tests/Feature directory:
php artisan make:test UserTest

Some arguments that can be passed to the Artisan test command:
php artisan test --testsuite=Feature --stop-on-failure

Profiling Tests
The Artisan test runner also includes a convenient mechanism for listing your application's slowest tests.
php artisan test --profile
