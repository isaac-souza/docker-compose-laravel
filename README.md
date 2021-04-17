# Docker-compose setup to run Laravel applications

## Available containers

- PHP-FPM 8 (localhost:8100, application)
- NGINX
- MySQL 5.7
- phpMyAdmin (localhost:8200)
- Redis 6
- MailHog (localhost:8025)

## How to use it?

### Step 1

Create a folder to hold the project files and navigate to it

```
mkdir laravel-docker
cd laravel-docker
```

### Step 2

Clone this repo

```
git clone https://github.com/isaac-souza/docker-compose-laravel.git .
```

### Step 3

Inside the folder, clone Laravel's repo to a folder called 'src'

```
git clone https://github.com/laravel/laravel.git src
```

### Step 4

Start the containers 

```
docker-compose up
```

### Step 5

When all containers finish booting up, run the following command in a new terminal window to install the Laravel dependencies

```
docker-compose exec -T app composer install
```

### Step 6

Create a copy of the .env.example file

```
docker-compose exec -T app cp .env.example .env
```

### Step 7

Generate a new encryption key

```
docker-compose exec -T app php artisan key:generate
```

### Step 8

Ajust a few .env variables

```
DB_HOST=mysql
REDIS_HOST=redis
```

### Step 9

Clear the config cache

```
docker-compose exec -T app php artisan cache:clear
```

### Step 10

Try to access the services in your browser

- Laravel app (http://localhost:8100)
- phpMyAdmin (http://localhost:8200)
- MailHog (http://localhost:8025)

## You are all set now!!!
