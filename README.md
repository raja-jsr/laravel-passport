install -> "laravel/framework": "5.8.*",

change the database name in env file

"laravel/passport": "7.5.1",
"lcobucci/jwt": "3.3.*", (paste to the composer.json then composer update)

php artisan migrate
php artisan passport:install

Add use Laravel\Passport\HasApiTokens; trait to the User model.
And use it tothe class like use HasApiTokens

Add use Laravel\Passport\Passport; to the AuthServiceProvider
And add Passport::routes();to the boot function

config/auth.php ->
'api' => [
        'driver' => 'passport',
        'provider' => 'users',
    ],
php artisan vendor:publish --tag=passport-migrations.
php artisan vendor:publish --tag=passport-components

route : http://127.0.0.1:8000/api/v1/user/login

php artisan serve

