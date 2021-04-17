# Docker-compose setup to run Laravel applications

## How to use it?

### Step 1

Clone this repo

```
git clone https://github.com/isaac-souza/docker-compose-laravel.git
```

### Step 2

Inside the folder, clone Laravel's repo to a folder called 'src'

```
git clone https://github.com/laravel/laravel.git src
```

### Step 3

Start the containers 

```
docker-compose up
```

### Step 4

When all containers finish booting up, run the following command in a new terminal window to install the Laravel dependencies

```
docker-compose exec -T app composer install
```

### Step 5

Create a copy of the .env.example file

```
docker-compose exec -T app cp .env.example .env
```

### Step 6

Generate a new encryption key

```
docker-compose exec -T app php artisan key:generate
```

### Step 7

Ajust a few .env variables

```
DB_HOST=mysql
REDIS_HOST=redis
```

### Step 8

Clear the config cache

```
docker-compose exec -T app php artisan cache:clear
```

### Step 9

Try to access Laravel's homepage

```
http://localhost:8100
```

## You are all set now!!!
