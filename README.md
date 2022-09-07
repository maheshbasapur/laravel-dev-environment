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
- Update /config/laratrust_seeder.php with right mapping of roles to permissions
- Run seeder to create permissions: php artisan db:seed
- Install Bootstrap with popperjs (optional) for UI
  - Run commands
    - npm install bootstrap
    - npm i @popperjs/core
    - npm install sass
    - npm install sass-loader
  - Create new file "resources/sass/app.scss" if not exist and add following
    - @import '~bootstrap';
  - To webpack.mix.js, add
    - mix.sass('resources/sass/app.scss', 'public/css')
  - Run command to compile
    - npm run dev
  - Add following to blade template files that need bootstrap
    - <link href="{{ asset('css/app.css') }}" rel="stylesheet">


Check registering new user and login

# References:
- https://www.linkedin.com/pulse/how-create-laravel-development-environment-using-docker-isaac-souza/