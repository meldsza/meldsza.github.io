---
layout: post
title: Configuration
category: laravel
date: 2017-05-21 17:50:00
---
All of the configuration files for the Laravel framework are stored in the config directory. 
### Environment Configuration
It is often helpful to have different configuration values based on the environment where the application is running. For example, you may wish to use a different database driver locally than you do on your production server.
To make this possible, Laravel utilizes the [DotEnv PHP library by Vance Lucas](https://github.com/vlucas/phpdotenv). 
In a fresh Laravel installation, the root directory of your application will contain a .env.example file. 
If you install Laravel via Composer, this file will automatically be renamed to .env. 
Otherwise, you should rename the file manually.

Your .env file **SHOULD NOT** be committed to your application's source control, since each developer / server using your application could require a different environment configuration. Furthermore, this would be a security risk in the event an intruder gain access to your source control repository, since any sensitive credentials like the DB password would get exposed.

### Retrieving Environment Configuration
All of the variables listed in this file will be loaded into the `$_ENV` PHP super-global when your application receives a request. 
However, it is recommended that you use the `env` helper to retrieve values from these variables in your configuration files. 
In fact, if you review the Laravel configuration files, you will notice several of the options already using this helper:
```php
'debug' => env('APP_DEBUG', false),
```
The second value passed to the env function is the "default value". This value will be used if no environment variable exists for the given key.

### Determining The Current Environment
The current application environment is determined via the `APP_ENV` variable from your `.env` file. You may access this value via the environment method on the `App` facade:
```php
$environment = App::environment();
```
You may also pass arguments to the environment method to check if the environment matches a given value. The method will return true if the environment matches any of the given values:
```php
if (App::environment('local')) {
    // The environment is local
}

if (App::environment('local', 'staging')) {
    // The environment is either local OR staging...
}
```

### Accessing Config variables
You may easily access your configuration values using the global config helper function from anywhere in your application. The configuration values may be accessed using "dot" syntax, which includes the name of the file and option you wish to access. A default value may also be specified and will be returned if the configuration option does not exist:
```php
$value = config('app.timezone');
```
To set configuration values at runtime, pass an array to the config helper:
```php
config(['app.timezone' => 'America/Chicago']);
```
### Configuration Caching
To give your application a speed boost, you should cache all of your configuration files into a single file using the ```config:cache`` Artisan command. This will combine all of the configuration options for your application into a single file which will be loaded quickly by the framework.

### Maintenance Mode
When your application is in maintenance mode, a custom view will be displayed for all requests into your application. This makes it easy to "disable" your application while it is updating or when you are performing maintenance. A maintenance mode check is included in the default middleware stack for your application. If the application is in maintenance mode, a `MaintenanceModeException` will be thrown with a status code of 503.
To enable maintenance mode, simply execute the down Artisan command:
```shell
php artisan down
```
You may also provide message and retry options to the down command. The message value may be used to display or log a custom message, while the retry value will be set as the Retry-After HTTP header's value:
```shell
php artisan down --message="Upgrading Database" --retry=60
```
To disable maintenance mode, use the up command:
```shell
php artisan up
```

The default template for maintenance mode responses is located in  `resources/views/errors/503.blade.php`, you can edit it to give your app a custom down page

