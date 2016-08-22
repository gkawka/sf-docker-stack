# Symfony Docker Stack
This repository provide full stack for running symfony application. It includes:
* `PHP Container` for holding your app sources and running php scripts
* `MySQL Container` for database
* `Nginx Container` for serving you app inside browser

## Setup
Place your source files inside `src` directory or initialize new project running command bellow:
```bash
docker-compose exec php /bin/bash -c "composer create-project -n symfony/framework-standard-edition app"
```

Modify `parameters.yml` file:
```yaml
# src/app/config/parameters.yml
parameters:
    ...
    database_host: db
    database_port: null
    database_name: symfony
    database_user: symfony
    database_password: symfony
    ...
```

## Running docker stack

```bash
docker-compose up -d
```

Inside your web browser navigate to [`http://localhost:8080`](http://localhost:8080).  

## Access dev environment
When you try to visit [`http://localhost:8080/app_dev.php`](http://localhost:8080/app_dev.php) you will bi noticed with:
```
You are not allowed to access this file. Check app_dev.php for more information.
```

To avoid this please remove IP address validation inside `src/web/app_dev.php`.

```
IMPORTANT: Do not upload app_dev.php file to your production environment
```

