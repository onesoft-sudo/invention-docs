# File & Folder Structure

A fresh invention-based project will look like this:

```
- project_root/
    - app/
        - Commands/
        - Events/
        - Exceptions/
        - Http/
            - Controllers/
            - Middleware/
            - Requests/
            - Resources/
            - Config.php
        - Initializers/
        - Models/
        - Policies/
    - config/
    - database/
        - factories/
        - migrations/
        - seeders/
    - public/
        - index.php
    - resources/
        - sass/
        - js/
        - views/
            - components/
            - errors/
            - layouts/
            welcome.power.php
    - routes/
        - api.php
        - auth.php
        - web.php
    - storage/
    - tests/
    - var/
        - cache/
        - dumps/
        - log/
        - tmp/
    - vendor/
    - .editorconfig
    - .env
    - .env.example
    - .gitignore
    - ChangeLog.md
    - composer.json
    - composer.lock
    - console
    - LICENSE
    - package.json
    - package-lock.json
    - README.md
    - webpack.config.js
    - webpack.development.js
    - webpack.production.js
```

A short overview of some important directories is given below.

### The `app/` directory
The `app/` directory contains almost 99% of the application code. Models, Controllers and Middleware are found here.

### The `config/` directory
This directory contains the application configuration files.

### The `database/` directory
This directory contains factories, migrations and seeders.

### The `public/` directory
This directory is the web server root. The `index.php` file in this directory is the entry point of the app.

<div class="alert alert-warning">
    <span class="alert-icon"></span>

    Never put any personal or sensitive information/file in `public` directory.
</div>

### The `resources/` directory
Static/dynamic assets such as javascript files, typescript files, css/sass files, images go here.

### The `routes/` directory
This directory contains all of the application routes.

### The `storage/` directory
This directory is for the application data storage. You can store uploaded files here.

### The `tests/` directory
PHPUnit tests directory.

### The `var/` directory
This is the variables directory. Runtime and temporary files, cache and log files go here.