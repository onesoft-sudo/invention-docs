# Basic Configuration

The first thing you should do is to edit the `.env` file. This file has all environment-related configuration variables.

### Database Connection
In the `.env` file, there are some `DB_` prefixed variables, these are related to database connection of your app.

- The `DB_VENDOR` is the database connection type you want to use. Default is MySQL. See the [valid values for this variable](#supported-database-vendors).
- The `DB_HOST` is the hostname of the database server.
- The `DB_PORT` is the port number of the database server.
- The `DB_USER` is the username that you want to use to authenticate with the database server.
- The `DB_PASSWORD` is the password for the given user.
- The `DB_NAME` is the database name on your database server. But if you're using SQLite, you need to specify an absolute path to the DB file in this variable. Also, in this case you only need to specify the `DB_VENDOR` and no other DB variable is required.


<div class="alert alert-warning">
    <span class="alert-icon"></span>

    Older versions of SQLite does not support some operations such as `ALTER...CHANGE` or `ALTER...DROP` etc, so there's a chance of loosing data if you do such operations with SQLite.
</div>

#### Supported Database Vendors
Currently invention only supports MySQL, MariaDB and SQLite. MySQL is recommended.

|Vendor Name|Value for `DB_VENDOR`|
|-----------|---------------------|
|MySQL      |mysql                |
|MariaDB    |mariadb              |
|SQLite     |sqlite               |

### Other Configurations

|Variable Name|Type   |Description                            |
|-------------|-------|---------------------------------------|
|TMP_DIR      |String |Temporary file storage directory.      |
|CACHE_DIR    |String |Cache file storage directory.          |
|CONF_DIR     |String |Configuration directory.               |
|APP_ENV_DEV  |Integer|Specify if the if is under development.|