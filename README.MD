# DOCKER PHP7.4

php7.4-fpm + nginx1.18 + mysql5.7 + node.js + composer. Php could be compiled with oci8.

documentation:
* [English-version](#English)
* [Russian-version](#Russian)

## English

Docker environment for developing php applications.
Consists of the following containers:
* php - php7.4-fpm + oci8
* nginx - nginx1.18
* mysql - mysql5.7
* node - node.js + npm
* composer - php + composer

Helps you quickly raise a development environment for your application.

### Preparing

1. Clone the repository.
1. If you have mac or windows, then in the docker settings in the file sharing section, allow the docker to mount the folder with the repository.
1. Create a .env file and register the variables (you can leave it unchanged). An example file is .env.example.

### Customization

The root directory for your project is located under the PROJECT_DIR path in the .env folder. By default it is ./shared/project.
The server redirects all requests to this folder. If you want to change this behavior, then the corresponding changes must be
add to docker-compose.yml (line 51) and to nginx config (in nginx folder).

### Launching

1. Run docker-compose up -d.
1. Run docker-compose ps and make sure php, mysql, nginx containers are working.
1. Open localhost.
1. Profit!!!

### Connecting to MYSQL

host: mysql.
Password, user and database are the same as in .env.

### Tuning

To change php or php-fpm settings, edit the corresponding files in the php directory.
You can also change the settings for mysql and nginx in the corresponding folders.
Don't forget to delete old images.

### Logs

All logs are located in ./shared/logs

### Bitrix

If the environment will be used for Bitrix development, you need to change lines 9 and 12 in nginx/Dockerfile.

### OCI8

If you need to build php with oci8, then you need to uncomment the section from line 10 in php / Dockerfile.

### COPYRIGHT AND LICENSE

This software is copyright (c) 2021 by Alexander Panteleev under MIT License.


## Russian

Докер среда для разработки php-приложения. 
Состоит из следующих контейнеров:
* php - php7.4-fpm + oci8
* nginx - nginx1.18
* mysql - mysql5.7
* node - node.js + npm
* composer - php + composer

Позволяет быстро развернуть среду разработки для вашего приложения.

### Подготовка

1. Склонируйте репозиторий.
1. Если у вас mac или windows, то в настройках докера в разделе file sharing разрешите докеру монтировать папку с репозиторием.
1. Создайте файл .env и пропишите переменные (можно оставить без изменений). Пример файла - .env.example.

### Настройка проекта

Корневая директория для вашего проекта находится по пути PROJECT_DIR в папке .env. По дефолту это ./shared/project.
Сервер все запросы переадресовывает в эту папку. Если вы хотите изменить это поведение, то соответствующие изменения надо
внести в docker-compose.yml (строка 51) и в настройку конфигурации nginx (в папке nginx).

### Запуск

1. Выполните docker-compose up -d.
1. Выполните docker-compose ps и убедитесь, что контейнеры php, mysql, nginx работают.
1. Откройте localhost.
1. Профит!!!

### Подключение к MYSQl

host: mysql.
Пароль, юзер и база данных такие же как в .env.

### Продвинутая конфигурация

Для изменения настроек php или php-fpm, отредактируйте соответствующие файлы в директории php.
Так же изменить настройки можно для mysql и nginx в соответствующих папках.
Не забудьте удалить старые изображения.

### Логи

Все логи находятся в ./shared/logs

### Битрикс

Если среда разработки будет использоваться под битрикс, то необходимо в nginx/Dockerfile изменить 9 и 12 строку.

### OCI8

Если сборка php нужна с oci8, то нужно раскоментировать в php/Dockerfile секцию с 10 строки.

### АВТОРСКИЕ ПРАВА И ЛИЦЕНЗИЯ

Это программное обеспечение защищено авторскими правами (c) 2021 Александра Пантелеева по лицензии MIT.

