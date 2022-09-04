# Set up Docker Environment for Laravel Development
- Create empty directories mysql/data --> for mysql files
- Create empty directories for redis/data --> for redis files
- Create empty directory src --> for the source code
- Clone laravel app code into src directory by
- Run command: docker-compose up -d --build --> to bring up the 
- Create .env file inside src directory
- Install dependancies by running command: docker-compose exec app composer install
- Generate app key: docker-compose exec app php artisan key:generate
- Check landing page by url: http://127.0.0.1:8100/
- Add Breeze dependancy for authentication: docker-compose exec app composer require laravel/breeze --dev
- Install breeze: docker-compose exec app php artisan breeze:install
- Run migrations: docker-compose exec app php artisan migrate

Check registering new user and login