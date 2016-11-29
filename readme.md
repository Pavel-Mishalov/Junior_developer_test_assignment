# ��������� Laravel 5.3.16 Framework � ������

������� ����� ������� PHPStorm:
������ ����� Composer Project Laravel Framework 5.3.16 
composer ����� �������� framework � ������
    
��� �������� ������ ��� ���������� ������ laracasts/Laravel-5-Generators-Extended
��� ����� ���� � Terminal:

```    
composer require laracasts/generators --dev
```
    
������� � `app/Providers/AppServiceProvider.php`, ��������������� ���:

```php
public function register()
    {
        if ($this->app->environment() == 'local') {
            $this->app->register('Laracasts\Generators\GeneratorsServiceProvider');
        }
    }
```
## �������� ��������
```
php artisan make:migration:schema create_positions_table --schema="position:string"
```

```
php artisan make:migration:schema create_workers_table --schema="full_name:string, work_position_id:integer:foreign, start_work:date, salary:integer"
```

```
php artisan make:migration:schema create_compani_structures_table --schema="subordinate:integer:foreing, supervisor:integer:foreing"
```

## ���������� ���� ������



## ���



## ���

