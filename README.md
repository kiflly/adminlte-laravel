#AdminLTE template Laravel 5 package
A Laravel 5 package that switch default Laravel scaffolding / boilerplate to AdminLTE template with Bootstrap 3.0 and Pratt Landing Page

See demo here:

 http://demo.adminlte.acacha.org/

If you are looking for the Laravel 4 version, use 0.1.5 version/tag and see [OLD-README.md](OLD-README.md)

[![Total Downloads](https://poser.pugx.org/acacha/admin-lte-template-laravel/downloads.png)](https://packagist.org/packages/acacha/admin-lte-template-laravel)
[![Latest Stable Version](https://poser.pugx.org/acacha/admin-lte-template-laravel/v/stable.png)](https://packagist.org/packages/acacha/admin-lte-template-laravel)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/acacha/adminlte-laravel/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/acacha/adminlte-laravel/?branch=master)
[![Code Coverage](https://scrutinizer-ci.com/g/acacha/adminlte-laravel/badges/coverage.png?b=master)](https://scrutinizer-ci.com/g/acacha/adminlte-laravel/?branch=master)
[![Build Status](https://scrutinizer-ci.com/g/acacha/adminlte-laravel/badges/build.png?b=master)](https://scrutinizer-ci.com/g/acacha/adminlte-laravel/build-status/master)
[![StyleCI](https://styleci.io/repos/35628567/shield)](https://styleci.io/repos/35628567)
[![Build Status](https://travis-ci.org/acacha/adminlte-laravel.svg?branch=master)](https://travis-ci.org/acacha/adminlte-laravel)
[![Dependency Status Composer](https://www.versioneye.com/user/projects/58483fc98c5dae004be97d36/badge.svg?style=flat-square)](https://www.versioneye.com/user/projects/58483fc98c5dae004be97d36)
[![Dependency Status Node.js](https://www.versioneye.com/user/projects/58483fc88c5dae0039a10ca5/badge.svg?style=flat-square)](https://www.versioneye.com/user/projects/58483fc88c5dae0039a10ca5)

# Installation & use

**So easy to install!** Install globally with composer:

```bash
composer global require "acacha/adminlte-laravel-installer=~3.0"
```

And convert any Laravel ~~fresh~~ (no need of fresh installation now thanks to [Acacha/llum](https://github.com/acacha/llum)) installation to AdminLTE/Pratt with:

```bash
laravel new laravel-with-admin-lte
cd laravel-with-admin-lte
adminlte-laravel install
```
Enjoy! If you wish you can use llum:

```bash
llum boot
```

To start using you Laravel with AdminLTE project. Llum will configure database (sqlite),execute migrations, install devtools and serve for you.

More info about llum commands in Github [Acacha/llum](https://github.com/acacha/llum).

IMPORTANT NOTE: on MAC OS you will have to replace BSD sed with GNU sed for example using brew:

```bash
brew install gnu-sed --with-default-names
```

#Requirements

This packages use (no need to install):

* [Composer](https://getcomposer.org/)
* [Laravel](http://laravel.com/)
* [AdminLTE](https://github.com/almasaeed2010/AdminLTE). You can see and AdminLTE theme preview at: http://almsaeedstudio.com/preview/
* [Pratt](http://blacktie.co/demo/pratt/). Pratt Landing Page
* [Acacha/user](https://github.com/acacha/user): providing boosted Laravel Users.
* [Acacha/llum](https://github.com/acacha/llum). Easy Laravel packages installation (and other tasks). Used to modify config/app.php file without using stubs (so you changes to this file would be respected)
* Acacha llum requires GNU sed. on MAC OS install GNU sed with:

```bash
brew install gnu-sed --with-default-names
```

This package assumes that you have in path your composer bin folder:
 
```
/YOUR_PATH_TO_HOME/.composer/vendor/bin
```

For example adding this line:

```bash
export PATH=${PATH}:~/.composer/vendor/bin
```

to your ~/.bashrc file

## Llum package

This package now uses [Acacha/llum](https://github.com/acacha/llum) to install packages, providers, aliases, etc in a current existing Laravel project.

Thanks to llum we can install adminlte-laravel package in any Laravel project no need of fresh installation.

However acacha/llum use bash scripts and commands like sed thta maybe are no compatible or not available in all platforms. No problem! You can use a backwards compatible version with:

 ```bash
 laravel new laravel-with-admin-lte
 cd laravel-with-admin-lte
 adminlte-laravel --no-llum install
 ```
 
Or you can use version 1.0 of installer with:
 
```bash
composer global require "acacha/adminlte-laravel-installer=~3.0"
```

## Laravel 5.3

Laravel 5.3 is the default Laravel version supported. See section Installation & use for more info. See below for info about how to install this package in older Laravel versions

### Laravel 5.3 manual installation

Follow the typical Laravel package installation steps:

<pre>
 laravel new laravel-with-admin-lte
 cd laravel-with-admin-lte
</pre>

Add admin-lte Laravel package with:

<pre>
 composer require "acacha/admin-lte-template-laravel:3.*"
</pre> 
 
To register the Service Provider edit **config/app.php** file and add to providers array:

```php
/*
* Acacha AdminLTE template provider
 */
Acacha\AdminLTETemplateLaravel\Providers\AdminLTETemplateServiceProvider::class,
```

To Register Alias edit **config/app.php** file and add to alias array:

```php
/*
* Acacha AdminLTE template alias
*/
'AdminLTE' => Acacha\AdminLTETemplateLaravel\Facades\AdminLTE::class,
```

Publish files with:

```php
php artisan vendor:publish --tag=adminlte --force
``` 
 
Use force to overwrite Laravel Scaffolding packages. That's all! Open the Laravel project in your browser or homestead machine and enjoy! 

## Laravel 5.2

Also you can use for previous version of Laravel (5.2) :

```
composer global require "acacha/adminlte-laravel-installer=~2.0"
laravel new --5.2 laravel-with-admin-lte
```

## Laravel 5.1 notes

By default Laravel 5.1 does not include default auth routes. Versions > 1.0 < 2.0 of this package add the necessary routes for you

See  [old README file](OLD-README.md) file for notes of which routes are registered.

###Installation

First install Laravel (http://laravel.com/docs/5.0/installation) and then Create a new Laravel project:

<pre>
 laravel new laravel-with-admin-lte
 cd laravel-with-admin-lte
</pre>

Add admin-lte Laravel package with:

<pre>
 composer require "acacha/admin-lte-template-laravel:1.*"
</pre> 
 
Register ServiceProvider editing **config/app.php** file and adding to providers array:

<pre>
// AdminLTE template provider         
Acacha\AdminLTETemplateLaravel\app\Providers\AdminLTETemplateServiceProvider::class,
</pre>

Publish files with:

<pre>
 php artisan vendor:publish --force --provider="Acacha\AdminLTETemplateLaravel\app\Providers\AdminLTETemplateServiceProvider"
</pre> 
 
Use force to overwrite Laravel Scaffolding packages. That's all! Open the Laravel project in your browser or homestead machine and enjoy! 

Note: use the following for Laravel <5.1 versions:

<pre>
 // AdminLTE template provider
 'Acacha\AdminLTETemplateLaravel\app\Providers\AdminLTETemplateServiceProvider',
</pre>

##Laravel Routes

This package installs Laravel routes that you will not find them at routes.php file. The routes installed by package would be find at file:

 https://github.com/acacha/adminlte-laravel/blob/master/src/Http/routes.php
 
A file included by AdminLTETemplateServiceProvider:

 https://github.com/acacha/adminlte-laravel/blob/master/src/Providers/AdminLTETemplateServiceProvider.php
 
You can override this routes by changing order of ServiceProviders in config/app.php file so if you put:

```php
App\Providers\RouteServiceProvider::class
```

After

```php
Acacha\AdminLTETemplateLaravel\Providers\AdminLTETemplateServiceProvider::class
```

Your routes in routes.php file will override default adminlte-laravel routes.

Also you can install manually the routes in routes.php file. Adminlte-laravel use same routes as Laravel make:auth command use, see:
 
https://github.com/laravel/framework/blob/5.2/src/Illuminate/Auth/Console/stubs/make/routes.stub
 
so you can add this lines to routes.php file:

```php
Route::auth();

Route::get('/home', 'HomeController@index');
```

And disable AdminLTETemplateServiceProvider in config/app.php file ( take into account that Adminte-laravel Facades and 
custom commands will not be available).

See issue https://github.com/acacha/adminlte-laravel/issues/69 for more info

##First steps, database creation, migrations and login

Once package installed you have to follow the usual steps of any laravel project to Login to the admin interface:

- Create a database. I recommend the use of laravel Homestead ()
- Create/check .env file and configure database acces (database name, password, etc)
- Run migrations with command $ php artisan migrate
- Registera a first user and Login with it

##AdminLTE

AdminLTE is a Free Premium Admin control Panel Theme That Is Based On Bootstrap 3.x created by Abdullah Almsaeed. See:

https://github.com/almasaeed2010/AdminLTE

## Avatar/Gravatar

Adminlte-laravel supports global recognized avatar (http://gravatar.com) using package creativeorange/gravatar (https://github.com/creativeorange/gravatar).

# Artisan Commands

## adminlte:publish | adminlte-laravel:publish

This command is already executed during installation using [acacha/llum](https://github.com/acacha/llum) but you can execute manually with:

```bash
php artisan adminlte:publish
```

Publish all necessary files from package to Laravel project.

## adminlte:sidebar | adminlte-laravel:sidebar

Only publish package sidebar to Laravel project allowing to customize sidebar:

```bash
php artisan adminlte:sidebar
```

Note: sidebar is already published when you use **adminlte-laravel install** command.

## adminlte:menu | adminlte-laravel:menu

Replaces sidebar view with a sidebar using [spatie/laravel-menu](https://github.com/spatie/laravel-menu):

```bash
php artisan adminlte:menu
```

This command also installs spatie/laravel-menu package and creates a default menu located **config/menu.php**.

## adminlte-laravel:admin | adminlte:admin

Executes make:adminUserSeeder artisan command (see next section) an executes seed. This command adds a default admin user to database.

```bash
php artisan adminlte:admin
File /home/sergi/Code/AdminLTE/acacha/adminlte-laravel_test/database/seeds/AdminUserSeeder.php created
User Sergi Tur Badenas(sergiturbadenas@gmail.com) with the environemnt password (env var ADMIN_PWD) created succesfully!
```

This command use (if exists) environment variables (.env file) ADMIN_USER, ADMIN_EMAIL and ADMIN_PWD. If this env variables does not exists then 
user git config (~/.gitconfig) to obtain data and if this info does not exists use Admin (admin@example.com) and password 123456 as default.

### make:adminUserSeeder

Create a new seed to add admin user to database. Use:

```bash
php artisan make:adminUserSeeder
File /home/sergi/Code/AdminLTE/acacha/adminlte-laravel_test/database/seeds/AdminUserSeeder.php created
```


# Roadmap

- Implement Facebook, Google and maybe twitter and github Login with Socialite
- Add email html templates
- Add breadcrumps with: https://github.com/davejamesmiller/laravel-breadcrumbs

## Documentation TODO

- Gulp file provided to compile Boostrap and AdminLTE less files
- Partial views (html header, content header, footer, etc.) to easily reuse code

## Packagist

https://packagist.org/packages/acacha/admin-lte-template-laravel

## More info

http://acacha.org/mediawiki/AdminLTE#adminlte-laravel

## Tests

Execute:

```
phpunit
```

In new created laravel project with acacha-admintle.laravel installed to test package is installed correctly.

## Social Login

FAQ:

How can I remove social login links in register and login pages?

Remove line @include('auth.partials.social_login') in files resources/views/auth/login.blade.php and register.blade.php

Social login links in login/register pages returns 404 not found

TODO: See package https://github.com/acacha/acacha-socialite

## Localization

All strings are localized using Laravel localization support: https://laravel.com/docs/master/localization

In your config/app.php file you can change locale to change language. You can install only localized files using tag  adminlte_lang:

```bash
php artisan vendor:publish --tag=adminlte_lang --force
```

The following languages are supported by default on this package: English, Catalan,Spanish and Brazilian Portuguese. Please feel free to submit a new pull request with another languages if you wish.

## Troubleshooting

### GNU sed on MAC OS

Acacha llum need GNU sed to work so replace BSD sed with GNU sed using:

```bash
brew install gnu-sed --with-default-names
```

Check you version of sed with:

```bash
man sed
```

sed GNU version path is:

```bash
$ which sed
/usr/local/bin/sed
```

Instead of default path of BSD sed (installed by default on MAC OS):

```bash
/usr/bin/sed
```

More info at https://github.com/acacha/adminlte-laravel/issues/58

## Change log

Please see [CHANGELOG](CHANGELOG.md) for more information what has changed recently.

## Testing

``` bash
$ composer test
```

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) and [CONDUCT](CONDUCT.md) for details.

## Security

If you discover any security related issues, please email :author_email instead of using the issue tracker.

## Credits

- [:author_name][link-author]
- [All Contributors][link-contributors]

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.

## See also

https://github.com/acacha/adminlte-laravel-installer

[ico-version]: https://img.shields.io/packagist/v/:vendor/:package_name.svg?style=flat-square
[ico-license]: https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square
[ico-travis]: https://img.shields.io/travis/:vendor/:package_name/master.svg?style=flat-square
[ico-scrutinizer]: https://img.shields.io/scrutinizer/coverage/g/:vendor/:package_name.svg?style=flat-square
[ico-code-quality]: https://img.shields.io/scrutinizer/g/:vendor/:package_name.svg?style=flat-square
[ico-downloads]: https://img.shields.io/packagist/dt/:vendor/:package_name.svg?style=flat-square

[link-packagist]: https://packagist.org/packages/:vendor/:package_name
[link-travis]: https://travis-ci.org/:vendor/:package_name
[link-scrutinizer]: https://scrutinizer-ci.com/g/:vendor/:package_name/code-structure
[link-code-quality]: https://scrutinizer-ci.com/g/:vendor/:package_name
[link-downloads]: https://packagist.org/packages/:vendor/:package_name
[link-author]: https://github.com/:author_username
[link-contributors]: ../../contributors