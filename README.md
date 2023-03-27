# EC-Cube v4 Example Project

Our [official guide](https://en.docs.smartpay.co/docs/ec-cube)([JA](https://ja.docs.smartpay.co/docs/ec-cube)) for EC-Cube integration.

## Prepare environment

Before getting started with the following steps, please make sure you have met [all the requirements](https://doc4.ec-cube.net/quickstart/requirement) provided by the official documentation.

Note: if you are on MacOS, most requirements are usually met by default. However, you might need to install PHP yourself instead of using the one that comes with the OS.

If you use [Homebrew](https://brew.sh/):

```shell
brew install php@7.4
brew link php@7.4
```

## Clone the project

Once the requirements are met, clone this repo and follow the steps below from the root directory of this project.

### Install Composer

Follow the [Composer official document](https://getcomposer.org/download/) to install `composer.phar` locally:

```shell
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') === '55ce33d7678c5a611085589f1f3ddf8b3c52d662cd01d4ba75c0ee0459970c2200a51f492d557530c71c15d8dba01eae') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"
```

### Install EC-Cube

```shell
php composer.phar create-project ec-cube/ec-cube ec-cube "4.2.1" --keep-vcs
```

If you plan to use EC-Cube 4.0, please use the following command to install it instead:

```shell
php composer.phar create-project ec-cube/ec-cube ec-cube "4.0.6" --keep-vcs
```

Then the next step is to install the Smartpay plugin. There are two methods to do it. The first is use the admin panel to do it. If you plan to use this method, please skip to the [Run the built-in web server
](#run-the-built-in-web-server) section.

The second method is to clone the repo into the EC-Cube folder:

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

### Open the admin panel

Open the admin panel with the URL:

```
http://localhost:8000/admin
```

The default credential is: `admin/password`

### Install Smartpay plugin by the EC-Cube admin panel

If you installed the Smartpay plugin already. Please skip this step.

To install the Smartpay plugin via the admin panel. You have to download the release package and upload it to the EC-Cube platform. The released packages files are at:

- For EC-Cube 4.0 https://github.com/smartpay-co/ec-cube/releases
- For EC-Cube 4.2 https://github.com/smartpay-co/smartpay-ec-cube42/releases

Download the latest version of the plugin package. Then follow the installation section in the [doccument](https://en.docs.smartpay.co/docs/ec-cube#installation)([JA](https://ja.docs.smartpay.co/docs/ec-cube#%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB)) to upload and install it.

### Further configurations

Then follow the configuration section in the [document](https://en.docs.smartpay.co/docs/ec-cube#configuration)
([JA](https://ja.docs.smartpay.co/docs/ec-cube#smartpay%E7%AE%A1%E7%90%86)) to complete the configuration.
