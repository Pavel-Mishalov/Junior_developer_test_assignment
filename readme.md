# Начало работы

### 1. Выбор среды разработки и сопотствующие программы:

- Среда разработки PHPStorm;
- Framework Laravel 5.3.16;
- Composer;
- Git.

### 2. Установка Laravel 5.3.16 Framework в проект

- Создал новый Composer Project Laravel Framework 5.3.16 composer сразу загрузил framework в проект;
- Так как проверка и разработка проводилась на локальном хосту и базой данных выбрана MySQL редактируем файл `.env`:

```
APP_DEBUG=true
APP_LOG_LEVEL=debug
APP_URL=http://localhost

DB_CONNECTION=mysql
DB_HOST=localhost
DB_DATABASE=migration_laravel
DB_USERNAME=root
DB_PASSWORD=
```

- В корень проекта создан файл `.htaccess`, который перенаправит все запросы на `server.php`:

```
AddDefaultCharset utf-8

RewriteEngine on
RewriteBase /

RewriteCond %(REQUEST_FILENAME) !-f
RewriteCond %(REQUEST_FILENAME) !-d

RewriteRule ^(.*)$ server.php
```

### 3. Установка вспомогательных плагинов.

- `Laravel ide helper`:

Загрузил последнюю версию с помощью `composer`:

```
composer require barryvdh/laravel-ide-helper
```

, после добавил поставщика услуг в  `providers` массив в `config/app.php`:

```php
Barryvdh\LaravelIdeHelper\IdeHelperServiceProvider::class,
```

- `Laravel 5 Generators Extended`

Загрузил последнюю версию с помощью `composer`:

```    
composer require laracasts/generators --dev
```
    
изменил в `app/Providers/AppServiceProvider.php`, соответствующий код:

```php
public function register()
    {
        if ($this->app->environment() == 'local') {
            $this->app->register('Laracasts\Generators\GeneratorsServiceProvider');
        }
    }
```
## Создание миграций
```
php artisan make:migration:schema create_positions_table --schema="position:string"
```

```
php artisan make:migration:schema create_workers_table --schema="full_name:string, work_position_id:integer:foreign, start_work:date, salary:integer"
```

```
php artisan make:migration:schema create_compani_structures_table --schema="subordinate:integer:foreing, supervisor:integer:foreing"
```

## Наполнение Базы данных
