# Getting Started


## Requirements

Your server/development computer must meet these requirements in order to run Invention Framework Apps:

- [PHP v7.4.0](https://www.php.net/releases/7_4_0.php) or higher
- [NodeJS](https://nodejs.org) JavaScript Runtime v12.0.0 or higher
- [PHP PDO](https://www.php.net/manual/en/book.pdo.php) extension with SQLite and MySQL driver
- [PHP JSON](https://www.php.net/manual/en/json.installation.php) extension

## Installation


You can install Invention using [Composer](https://getcomposer.org):


```
composer create-project osn/invention myapp
```

This will create an Invention project in `myapp/` directory.


## Quick start

Make sure that PHP is installed globally, otherwise the app might not work properly.
Go to your project directory and run:

```
npm install
npm run dev
php console serve
```


The first command installs the project dependencies, the second one compiles the javascript and css files and puts them into the `public/` folder and the last ommand starts a local development server (PHP's built in dev server) at [localhost:8080](http://localhost:8080).

You can now open http://localhost:8080 using your favourite browser.