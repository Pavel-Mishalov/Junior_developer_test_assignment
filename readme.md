# установка Laravel 5.3.16 Framework в проект

Рабочая среда выбрана PHPStorm:
Создал новый Composer Project Laravel Framework 5.3.16 
composer сразу загрузил framework в проект
    
Для удобства работы был установлен плагин laracasts/Laravel-5-Generators-Extended
для этого ввел в Terminal:

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



## Еще



## Еще

