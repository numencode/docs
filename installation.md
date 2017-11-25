# Installation

- [Installation](#installation)
    - [Server Requirements](#server-requirements)
    - [Installing Numencode CMS](#installing-numencode-cms)
    - [Configuration](#configuration)
    - [Admin Dashboard](#admin-dashboard)
- [Web Server Configuration](#web-server-configuration)
    - [Pretty URLs](#pretty-urls)

<a name="installation"></a>
## Installation

Numencode CMS in built on top of the Laravel framework so in order for it to work, your will need to make sure your server meets the same requirements as it would for the Laravel installation.

<a name="server-requirements"></a>
### Server Requirements

The Numencode CMS has a few system requirements. Of course, all of these requirements are satisfied by the [Laravel Homestead](/docs/{{version}}/homestead) virtual machine, so it's highly recommended that you use Homestead as your local Numencode CMS development environment.

However, if you are not using Homestead, you will need to make sure your server meets the following requirements:

- PHP >= 7.0.0
- OpenSSL PHP Extension
- PDO PHP Extension
- Mbstring PHP Extension
- Tokenizer PHP Extension
- XML PHP Extension

<a name="installing-numencode-cms"></a>
### Installing Numencode CMS

Numencode CMS utilizes [Composer](https://getcomposer.org) to manage its dependencies. So, before using it, make sure you have Composer installed on your machine.
Numencode CMS also requires a database (e.g. MySQL) for it to work, so prepare an empty database with associeated username and password before installation.

#### Step 1

Clone the Numencode CMS repository to your project directory:
```bash
$ git clone https://github.com/BlazOrazem/numencode.git
```

#### Step 2

Navigate to your project directory, make sure you have [Composer](https://getcomposer.org/) installed on your system and run:
```bash
$ composer install
```

#### Step 3

When Composer finishes installing dependencies, run Numencode CMS installer:
```bash
$ php artisan project:install
```

<a name="configuration"></a>
### Configuration

Check file .env.example for more configurations and copy desired settings to your .env file.

Be sure to check **/config/numencode.php** file for some more application settings.

<a name="admin-dashboard"></a>
### Admin Dashboard

The URL for the admin dashboard should be your APP_URL (in .env file) followed by /admin, e.g.: 

    http://www.numencode.app/admin

The manager credentials are set by the php artisan project:install command.



<a name="configuration"></a>
### Configuration

#### Numencode CMS Configuration

Check file .env.example for more configurations and copy desired settings to your .env file.
Be sure to check **/config/numencode.php** file for some more application settings.

#### Public Directory

After installing Numencode CMS, you should configure your web server's document / web root to be the `public` directory. The `index.php` in this directory serves as the front controller for all HTTP requests entering your application.

#### Configuration Files

All of the configuration files for the Laravel framework are stored in the `config` directory. Each option is documented, so feel free to look through the files and get familiar with the options available to you.

#### Directory Permissions

After installing Numencode CMS, you may need to configure some permissions. Directories within the `storage` and the `bootstrap/cache` directories should be writable by your web server or Laravel will not run.

#### Additional Configuration

Numencode CMS needs almost no other configuration out of the box. You are free to get started developing! However, you may wish to review the `config/app.php` file and its documentation. It contains several options such as `timezone` and `locale` that you may wish to change according to your application.

<a name="web-server-configuration"></a>
## Web Server Configuration

<a name="pretty-urls"></a>
### Pretty URLs

#### Apache

Laravel includes a `public/.htaccess` file that is used to provide URLs without the `index.php` front controller in the path. Before serving Laravel with Apache, be sure to enable the `mod_rewrite` module so the `.htaccess` file will be honored by the server.

If the `.htaccess` file that ships with Laravel does not work with your Apache installation, try this alternative:

    Options +FollowSymLinks
    RewriteEngine On

    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteRule ^ index.php [L]

#### Nginx

If you are using Nginx, the following directive in your site configuration will direct all requests to the `index.php` front controller:

    location / {
        try_files $uri $uri/ /index.php?$query_string;
    }

Of course, when using [Homestead](/docs/{{version}}/homestead) or [Valet](/docs/{{version}}/valet), pretty URLs will be automatically configured.