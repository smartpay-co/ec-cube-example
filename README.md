# EC-Cube v4 Example Project

## Get started

Before getting started with the following steps, please make sure you have met [all the requirements](https://doc4.ec-cube.net/quickstart/requirement) provided by the official documentation.

### Clone this repo

Once all the requirements are met, clone this repo and follow the steps below from the root directory of this project.

### Composer

```shell
curl -sS https://getcomposer.org/installer | php # install composer
php composer.phar selfupdate --1
php composer.phar create-project ec-cube/ec-cube ec-cube "4.0.x-dev" --keep-vcs
```

### Clone Smartpay plugin into the EC-Cube directory

```shell
cd ec-cube
git clone https://github.com/smartpay-co/ec-cube app/Plugin/Smartpay
```

### Install and enable Smartpay

```shell
./bin/console eccube:plugin:install --code=Smartpay
./bin/console eccube:plugin:enable --code=Smartpay
```

### Run the built-in web server

```shell
php -S 127.0.0.1:8000
```

### Open the admin panel for further configurations

```shell
open http://localhost:8000/admin # default credentials: admin/password
```
