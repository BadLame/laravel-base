# Laravel-base
___

### Локальная установка

#### Пререквизиты
- Установленный `php >= 8.1`
- Установленный `nodejs` ~ 14-16 версий
- Установленный `npm`
- Установленный и запущенный `docker` (наиболее удобный способ локальной установки проекта)

#### Запуск

1)
 ```shell
 cp .env.example .env
 composer install
 php artisan key:generate
 ```

2) С помощью комманды `id` узнать id текущего пользователя и группы, подставить в `.env` в переменные `WWWGROUP`, `WWWUSER`

3)
 ```shell
 sudo -s # все операции с докером должны быть от рута
 ./vendor/bin/sail up -d # можно сделать alias `sail` в `/root/.bashrc`
 sail artisan migrate
 sail artisan db:seed
 sail artisan passport:install # сгенерит необходимые вещи для авторизации через `laravel-passport`
 sail npm i # или выполнять из другой консоли от обычного пользователя (без sail)
 sail npm run dev # или выполнять из другой консоли от обычного пользователя (без sail)
 # ./vendor/bin/sail down # остановка докер-контейнеров
 ```


### Установка на прод

#### Запуск

[comment]: <> (Не забыть про `php artisan passport:install & passport:keys` при первом запуске)
