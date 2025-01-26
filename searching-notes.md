## Laravel Artisan Commands
> Comprehensive :100: documentation on Laravel artisan commands :partying_face:.

## Table of Contents
- [Terms](#terms)
- [Differences Between Composer Files](#differences-between-composer-files)
- [Differences Between Artisan and Index Files](#differences-between-artisan-and-index-files)
- [Http Directory](#http-directory)
- [Differences Between Mocks and Stubs](#differences-between-mocks-and-stubs)
- [Encryption](#encryption)
- [RFC vs IETF](#rfc-vs-ietf)
- [TLS](#tls)
- [PSR](#psr)
- [PSR-7](#psr-7)
- [ECMAScript vs PSR](#ecmascript-vs-psr)
- [Proxy Servers](#proxy-servers)
- [PHP output buffering functions](#php-output-buffering-functions)
- [Blade vs React](#blade-vs-react)
- [WSL1 vs WSL2](#wsl1-vs-wsl2)
- [Vite Development Process](#vite-development-process)
- [Database](#database)
- [Database Optimization](#database-optimization)
- [Illuminate Database Eloquent Attributes](#illuminate-database-eloquent-attributes)
- [Searching](#searching)
- [Blue Green Deployment Strategy](#blue-green-deployment-strategy)

## Terms
- Major:Minor:Patch Releases &rarr; 1.2.3
- Alpha and Beta versions.
- Direct Dependencies and Transitive Dependencies.
- Breeze and Jetstream are Laravel packages used for authentication.
> Choose Breeze if you need simple auth scaffolding, and Jetstream if you want a robust application with features like team management and two-factor authentication.
- Laravel Shift is used to upgrade Laravel applications.
- Forge, Vapor, and Envoyer are for deployment, but they require a subscription to use.
- Laravel Cashier, Spark, and Stripe are used to handle subscriptions and billings.
- Laravel Sail is a lightweight command-line interface for Laravel that provides a simple and convenient way to set up a local development environment using Docker, Removing the `it works on my machine` problem.
- Passport, Socialite, OAuth2, and Sanctum are used to build APIs.
- Laravel Telescope, Pulse, and Debugbar are powerful tools for debugging and monitoring Laravel applications.
- Laravel Dusk is an automation tool for browser testing.
- Termwind allows you to build command-line interfaces (CLI) using web-like styling.
- Redis and Memcached are an in-memory data structure used for `Caching`, `Session Store`, and `Queue Management`.
- Laravel Pail is to interact with application logs directly from the command line.
> It requires the `pcntl` extension witch is not available on Windows.
- Ziggy is a Laravel package that provides an easy way to use Laravel's named routes in JavaScript. It generates a JavaScript object containing all the named routes defined in your Laravel application.
- Bootstrap is a self-starting process.
- Laracon stands for Laravel conference.
- SSH: Secure Shell.
- SSL: Secure Sockets Layer.
- Inertia is an adapter for your frontend JavaScript frameworks.
- `Tailwind` is a `Postcss` plugin, `Vite` automatically apply `postcss.config.js` file.

## Differences Between Composer Files
1. composer.json:
   - Manages the desired packages and version ranges.
   - Manually edited by developers.
2. composer.lock:
   - Manages the exact versions of the installed packages.
   - Automatically generated and updated by composer when installing or updating dependencies.

## Differences Between Artisan and Index Files
- **artisan:**
    - Located in the root directory.
    - Handles CLI commands for tasks like migrations, scaffolding, and queue management.
    - Outputs text to the terminal.
    - Triggered when running commands in the terminal (php artisan).
- **index.php:**
    - Located in the public directory.
    - Handles HTTP requests for web traffic.
    - Outputs responses like HTML/JSON to users via the browser.
    - Triggered when accessing the app through a web server (e.g., Apache/Nginx).

## Http Directory
- **Controllers:** Handle incoming HTTP requests.
- **Middleware:** Filter incoming HTTP requests.
- **Requests:** Validate incoming HTTP requests.

## Differences Between Mocks and Stubs
- Mocking allows you to simulate database behavior.
- Stubs return pre-defined data when called.
- Both of them are used to test your logic in isolation.

## Encryption
- A key is used to configure a cryptosystem.
- A `symmetric key` cryptosystem uses the same key to encrypt and decrypt.
- A public key `asymmetric key` cryptosystem uses a public key to encrypt and a private key to decrypt.
- Identical plaintexts yield different ciphertexts.
- `AES-256-CBC` Stands for advanced Encryption Standard 256 Cipher Block Chaining.

## RFC vs IETF
- [Requests for Comments](https://www.rfc-editor.org/rfc) published by the Internet Engineering Task Force.
- Notable RFCs:
    - RFC 7239: Forwarded HTTP Extension.
    - RFC 791: Defines the Internet Protocol (IP).
    - RFC 6269: Defines Issues with IP Address Sharing.
    - RFC 2616: Defines HTTP/1.1.
    - RFC 7230: Hypertext Transfer Protocol (HTTP/1.1): Message Syntax and Routing.
    - RFC 5246: Defines Transport Layer Security (TLS).

## TLS
- **TLS Certificate:** Transport Layer Security Certificate.
- **Security:** Encrypts data `such as passwords, credit card numbers, and personal information` to protect against hackers.
- **Trust:** Increases user trust with visual cues like the padlock symbol and HTTPS in the browser.
- **SEO:** Google gives ranking boosts to websites that use HTTPS over HTTP.

## PSR
- PHP Standard Recommendations.
- **PSR-1:** Basic Coding Standard.
- **PSR-2:** Coding Style Guide.
- **PSR-4:** Autoloading.
- **PSR-7:** HTTP Interface.

## PSR-7
- interface `MessageInterface`
- interface `RequestInterface` extends `MessageInterface`
- interface `ResponseInterface` extends `MessageInterface`
- interface `ServerRequestInterface` extends `RequestInterface`
- interface `UriInterface`
- interface `StreamInterface`
- interface `UploadedFileInterface`

## ECMAScript vs PSR
- ECMAScript: language specification `updates` upon which JavaScript based.
- PSR: discusses PHP coding style, framework interoperability, or standardized practices in PHP development.

## Proxy Servers
- Anonymity and Geolocation Bypass:
    - Proxy servers can hide the client's actual IP address, making it appear as though the request is coming from the proxy server rather than the client. This helps protect the user's identity and location.
    - Proxies can allow users to bypass geographic restrictions by making it seem as though their requests are coming from a different location.
- Security and Content Filtering:
    - Proxies can act as a firewall or filtering system, blocking malicious traffic and preventing access to certain websites. This is often used in corporate environments for network security.
    - Organizations use proxy servers to restrict access to certain websites. For example, a company might block social media sites for its employees.
- Caching:
    - Proxy servers can store copies of frequently accessed resources (like web pages or files), making subsequent requests faster since the data can be retrieved from the proxy’s cache instead of the actual server.
- Finally:
    - A proxy server acts as an intermediary between a client (such as a user's computer or browser) and the internet. When a client makes a request to access a website or other online resource, the request can first go through a proxy server, which then forwards the request to the destination. The response from the destination is also passed back to the client via the proxy server.

## PHP output buffering functions
- `ob_start()` Starts output buffering.
- `ob_flush()` Sends the current buffer contents to the browser but keeps buffering enabled.
- `ob_end_flush()` Sends the contents of the output buffer to the browser and turns off output buffering.
- `ob_end_clean()` Clears (discards) the contents of the output buffer and turns off output buffering. No output is sent.
- `ob_get_contents()` Returns the current contents of the output buffer as a string, allowing you to inspect or manipulate it before it is sent.

## Blade vs React
- Blade:
    - Server-Side Rendering.
    - Multi-Page Applications.
    - Fast Initial Page Loading.
    - SEO is a primary concern.
- React:
    - Client-Side Rendering.
    - Single Page Applications `for state handling`.
    - Real-Time Updates.
    - SEO is not a primary concern.
- They can be used together in hybrid applications.

## WSL1 vs WSL2
- WSL1: Uses a compatibility layer to translate Linux system calls into Windows system calls. This layer enables Linux binaries to run on Windows without requiring a Linux kernel.
- WSL2: Runs a real Linux kernel inside a lightweight virtual machine (VM). This is closer to how a native Linux environment operates.

## Vite Development Process
- Blade Changes:
    - When you edit a Blade file the `laravel-vite-plugin` detects the change, since Blade files aren't directly part of the HMR system, the plugin triggers a full browser refresh to reflect the updated Blade content.
- CSS/JS Changes:
    - When you edit a CSS or JavaScript file listed in the input array of `vite.config.js`, Vite’s HMR updates only those assets in the browser without reloading the entire page and losing the state of the application.

## Database
- MariaDB was Created by the original developers of MySQL as a fork of MySQL after the Oracle acquisition to ensure it remains free and open source.
> The MariaDB Foundation maintains MariaDB.
- SQL is a set of commands for interacting with relational database management systems (RDBMS).

## Database Optimization
- Indexing
- Query Optimization
- Normalization
- Caching
- Connection Pooling
- Efficient Data Types
- Remove Unused Data from Frequently Accessed Tables
- Monitoring and Performance Tuning `slow query log`
- Concurrency Management `how multiple users or processes interact with the database`

## Illuminate Database Eloquent Attributes
- **CollectedBy:** Specify a custom collection.
    - Target: Model class.
- **ObservedBy:** Specify an observer.
    - Target: Model class, Repeatable.
- **ScopedBy:** Specify a query scope.
    - Target: Model class, Repeatable.

## Searching
- `Elasticsearch`, `Algolia`, and `Meilisearch` are search engines (search-as-a-service platforms) These search engines are optimized for speed and can handle very large amounts of data (millions or even billions of records) without significant performance degradation. They use indexing techniques to make searches extremely fast.
- `Fuzzy Matching` and `Typo Tolerance` allow searches to find results even if there are slight misspellings or variations.
- `Faceting` is the count of available options.

## Blue Green Deployment Strategy
- **What it is?**
    - It is a software release management approach aimed at minimizing downtime and reducing risk when deploying new versions of an application or service. It achieves this by maintaining two separate environments:
    - **Blue environment:** Represents the current live/production version of the application that users are actively using.
    - **Green environment:** Represents the new version of the application that is prepared, tested, and ready to be deployed.
- **How it works:**
    - **Prepare the Green Environment:** Developers and operations teams set up the new version of the application (the `Green` environment) and ensure it is configured identically to the `Blue` environment.
    - **Test the Green Environment:** The `Green` environment is thoroughly tested to ensure it is stable and meets all requirements.
    - **Switch Traffic:** Once the `Green` environment is ready, traffic is switched from the `Blue` environment to the `Green` environment. This is typically achieved using tools like load balancers, DNS updates, or service meshes.
    - **Monitor the Green Environment:** After the traffic switch, the `Green` environment is closely monitored for any issues. If there are no problems, the `Green` environment becomes the new production environment.
    - **Roll Back if Needed:** If issues arise in the `Green` environment, traffic can be switched back to the `Blue` environment, providing a quick rollback mechanism.
    - **Retire the Old Version:** Once the new version is confirmed to be working smoothly, the `Blue` environment can be retired.
- **Benefits:**
    - **Minimal Downtime:** Swapping traffic between environments ensures minimal disruption for users.
    - **Quick Rollback:** In case of failures, traffic can be redirected to the previous version without significant delays.
    - **Testing in Production-Like Environments:** The `Green` environment can mirror production, allowing for realistic testing before deployment.
    - **Improved Reliability:** Reduces the risk associated with deploying updates.
- **Challenges:**
    - **Cost:** Maintaining two separate environments can be expensive, especially for resource-intensive applications.
    - **Environment Synchronization:** Ensuring both environments are identical can be challenging.
    - **Complexity:** Managing traffic switching and monitoring adds operational complexity.
- **Use Case Scenarios:**
    - Deploying updates in applications where downtime is not acceptable (e.g., e-commerce platforms or financial systems).
    - Systems that demand high availability and reliability.
