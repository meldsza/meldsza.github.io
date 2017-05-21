---
layout: post
title: Setting Up
category: laravel
date: 2017-05-21 17:25:00
---
### Requirements  
The Laravel framework has a few system requirements. You could use [Laravel Homestead](https://laravel.com/docs/5.4/homestead) or manually satisfy the below requirements
- PHP >= 5.6.4
- OpenSSL PHP Extension
- PDO PHP Extension
- Mbstring PHP Extension
- Tokenizer PHP Extension
- XML PHP Extension
### Installing Laravel  
First, we download the Laravel installer using Composer:
```shell
composer global require "laravel/installer"
```
Once installed, the `laravel new` command will create a fresh Laravel installation in the directory you specify. For instance, `laravel new my-awesome-site` will create a directory named `nmy-awesome-site` containing a fresh Laravel installation with all of Laravel's dependencies already installed:
```shell
laravel new my-awesome-site
```
Alternatively, you may also install Laravel by issuing the Composer `create-project` command:
```shell
composer create-project --prefer-dist laravel/laravel my-awesome-site
```

### Starting up
To start the server, just do
```shell
php artisan serve
```
and it will serve the site with the default php server
You could also set it to listen to a particular port using the `--port` flag
```shell
php artisan serve --port=8080
```

If your stuck somewhere, you could refer to the [Installation Documentation on laravel.com](https://laravel.com/docs/5.4/installation)
