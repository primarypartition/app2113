# Project Setup

> https://symfony.com/

> https://symfony.com/doc/current/setup.html

> composer create-project symfony/skeleton app2113

> php -S 127.0.0.1:8000 -t public

> symfony server:start

> composer dump-autoload

> composer create-project symfony/website-skeleton ./ "4.2.*"

``` 
<VirtualHost *:80>   
	ServerName local.app2113
	DocumentRoot "C:\xampp\htdocs\app2113\public" 
</VirtualHost>
```

```
127.0.0.1        local.app2113
```

> https://symfony.com/download

> symfony check:requirements

> composer require symfony/requirements-checker

> http://local.app2113/check.php

> composer remove symfony/requirements-checker

> bin/console make:controller ToDoListController

> bin/console make:entity 

```
Task
title
string
255
yes
status
boolean
yes
```


# Symfony Packages

> https://flex.symfony.com/

> composer require symfony/maker-bundle --dev

> composer require annotations

> composer require symfony/apache-pack

> composer require twig-bundle

> composer require orm

> composer require doctrine

> composer require doctrine/annotations

> composer require logger

> composer require symfony/flex

> composer require maker

> composer require symfony/asset

> composer require symfony/security-bundle

> composer require orm-fixtures --dev

> composer require sensio/framework-extra-bundle

> composer require web-profiler-bundle

> composer require symfony/debug-bundle

> composer require symfony/proxy-manager-bridge

> composer require symfony/cache

> composer require symfony/event-dispatcher

> composer require symfony/form

> composer require symfony/validator doctrine/annotations

> composer require symfony/swiftmailer-bundle

> composer require browser-kit css-selector --dev

> composer require --dev symfony/phpunit-bridge phpunit/phpunit symfony/test-pack

> composer require symfony/orm-pack symfony/form symfony/security-bundle symfony/validator

> composer require sensiolabs/security-checker

> composer require symfony/expression-language

> sudo apt-get install php-xdebug

> composer require symfony/translation


# Git Repo Setup 

```
git init
git add .
git commit -m "project init"
git remote add origin https://github.com/primarypartition/app2113.git
git push -u origin master
```


# Database 

> composer require doctrine

> composer require doctrine/annotations

> composer require orm

> .env

```
DATABASE_URL="sqlite:///%kernel.project_dir%/var/data.db"
```

> bin/console doctrine:database:create
 
> bin/console make:entity

> bin/console make:migration

> bin/console doctrine:migrations:migrate

> bin/console list doctrine

> bin/console doctrine:schema:drop -n -q --force --full-database

```
bin/console doctrine:schema:drop -n -q --force --full-database &&
rm migrations/*.php &&
bin/console make:migration &&
bin/console doctrine:migrations:migrate -n -q 
```

> bin/console doctrine:fixtures:load -n -q

> bin/console make:entity Video

> php bin/console make:migration

> php bin/console doctrine:migrations:migrate

> bin/console make:entity Address

> php bin/console make:migration

> php bin/console doctrine:migrations:migrate

> php bin/console doctrine:fixtures:load

> bin/console debug:autowiring


# Commands

> bin/console

> bin/console make:controller WelcomeController

> bin/console doctrine:database:create

> bin/console make:entity

> bin/console make:migration

> bin/console doctrine:migrations:migrate

> bin/console debug:container

> bin/console cache:clear

> bin/console list doctrine

> bin/console doctrine:fixtures:load -n -q

> bin/console debug:router

> bin/console debug:autowiring

> bin/console help make:migration

> bin/console about

> bin/console debug:event-dispatcher

> bin/console debug:event-dispatcher kernel.request

> bin/console make:subscriber

> bin/console make:form VideoFormType

> bin/console swiftmailer:spool:send --time-limit=10

> bin/console make:functional-test

> bin/console make:test

> ./bin/phpunit

> php bin/phpunit

> vendor/bin/phpunit

> php bin/phpunit --coverage-test

> bin/console make:user

> bin/console security:check 

> bin/console make:voter


# .htaccess file in public folder

```
<IfModule mod_rewrite.c>
    Options -MultiViews
    RewriteEngine On
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteRule ^(.*)$ index.php [QSA,L]
</IfModule>

<IfModule !mod_rewrite.c>
    <IfModule mod_alias.c>
        RedirectMatch 302 ^/$ /index.php/
    </IfModule>
</IfModule>
```


# Webpack Encore

> npm init

> npm install @symfony/webpack-encore --save-dev

> npm install --save jquery

> touch webpack.config.js

```
var Encore = require('@symfony/webpack-encore');

Encore
    .setOutputPath('public/build/')
    .setPublicPath('/build')
    .addEntry('js/custom', './build/js/custom.js')
    .addStyleEntry('css/custom', ['./build/css/custom.css'])
    // .autoProvidejQuery()
;

module.exports = Encore.getWebpackConfig();
```

> ./node_modules/.bin/encore production

> ./node_modules/.bin/encore dev --watch
