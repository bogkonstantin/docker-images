PHP 7.4 FPM  
Xdebug 3  
Composer 2  
PHP Unit 7  
NodeJS 12  
Yarn  
User `www-data`

Use it, for example, for Symfony or Laravel local development without frontend.

docker-compose.yml sample:
```yaml
version: '3'

services:
  php:
    image: bogkonstantin/php-7.4-node-12-debug:latest
    environment:
      XDEBUG_CONFIG: "client_host=172.17.0.1 client_host=9003"
      PHP_IDE_CONFIG: serverName=localhost
    volumes:
      - ./src:/var/www/src
```
