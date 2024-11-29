# Laravel 11.x Scaffold Generator

> Fork from summer's https://github.com/summerblue/generator


[![Travis](https://img.shields.io/travis/aobozhang/generator.svg?style=flat-square)](https://github.com/aobozhang/generator)
[![Packagist](https://img.shields.io/packagist/dt/aobozhang/generator.svg?style=flat-square)](https://packagist.org/packages/aobozhang/generator)
[![Tag](https://img.shields.io/github/tag/aobozhang/generator.svg)](https://github.com/aobozhang/generator/tags)

Laravel Scaffold Generator, for Laravel 11.x.

## Install

```
<!-- composer.json -->
{
   ...

   "repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/aobozhang/generator"
        }
    ],
   
   ...

    "require-dev": {
         ...
         "summerblue/generator": "dev-master"
    }
    
    ...
}

```

```
<!-- console -->
composer update
```

## Usage
```
php artisan make:scaffold [model-name] --schema=[name:type:index|unsigned|nullable|default(?)]
```

## Examples
```
php artisan make:scaffold Projects --schema="name:string:index,description:text:nullable,subscriber_count:integer:unsigned:default(0)"
```

This command will generate:

```
$ php artisan make:scaffold Projects --schema="name:string:index,description:text:nullable,subscriber_count:integer:unsigned:default(0)"


----------- scaffolding: Project -----------

+ ./database/migrations/2017_04_17_065656_create_projects_table.php
+ ./database/factories/ModelFactory.php
+ ./database/seeders/ProjectsTableSeeder.php
+ ./database/seeders/DatabaseSeeder.php (Updated)
x ./app/Models/Model.php (Skipped)
+ ./app/Models/Project.php
+ ./app/Http/Controllers/ProjectsController.php
x ./app/Http/Requests/Request.php (Skipped)
+ ./app/Http/Requests/ProjectRequest.php
+ ./app/Observers/ProjectObserver.php
+ ./app/Providers/AuthServiceProvider.php (Updated)
+ ./routes/web.php (Updated)

--- Views ---
   + create_and_edit.blade.php
   + index.blade.php
   + show.blade.php
x ./resources/views/error.blade.php
Migrated: 2017_04_17_065656_create_projects_table

----------- -------------------- -----------
-----------   >DUMP AUTOLOAD<    -----------
```

## Explain

Generate the following:

- Migration
- Seed, add ModelFactory entry, and DatabaseSeeder entry
- Base Model class, Model and helper trait
- Resource Controller
- Base FormRequest class and StoreRequest, UpdateRequest
- **[x]** ~~Policy and Policy base class, auto register AuthServiceProvider class~~
- Update routes file to register resource route
- Add error page view
- Create and Edit action share the same view

## Future Plan

- no plan

## Screenshot

![file](https://cloud.githubusercontent.com/assets/324764/22488519/7466a638-e84d-11e6-8201-99ad377d6270.png)

## Thanks to
- [laralib/l5scaffold](https://github.com/laralib/l5scaffold)
- [summerblue/generator](https://github.com/summerblue/generator)
