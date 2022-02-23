# Intro to the Models

The models are simple class which works as a wrapper for your application data. They provide an elegant way to interact with your database and process data. You can imagine that each model instance is an indivisual row of a database table.

### Creating your first model

Alright, open the command line and run:

```php
php console make:model Post
```

This will create a new model at `app/Models/` with the name of `Post`. There is a simple relation between the table names and model names. Models must have a matching name with its corresponsing table, but it should be singular. For tables, it must be plural. You can think that there exists a table named `posts` in our DB.<br>
The newly created model should look like this:

```php
<?php

namespace App\Models;


use OSN\Framework\Core\Model;
use OSN\Framework\Database\HasFactory;

class Post extends Model
{
    use HasFactory;
}
```

For now, there is no need to edit this file. Let's create the `posts` table and add some data to it now:

MySQL/MariaDB:
```sql
CREATE TABLE posts(
    id INT NOT NULL UNIQUE AUTO_INCREMENT,
    title TEXT NOT NULL,
    PRIMARY KEY (id)
)
```

SQLite:
```sql
CREATE TABLE posts(
    id INT NOT NULL PRIMARY KEY,
    title TEXT NOT NULL
)
```

Add data to the table:

id|title
--|-----
1 | Foo
2 | Bar
3 | Car
4 | Cat
5 | PHP

Now let's go to an action method of a live controller in the app and fetch all data with the model:

```php
public function index()
{
    $data = \App\Models\Post::all(); /* Use all() method fetch all the data from the corresponding table. Returns an \OSN\Framework\Core\Collection object which is equivalent to an array */
    return $data;
}
```
 
So the `$data` will hold all the data. Now invention is intelligent enough to check if the controller action is returning an array/object and if it is then convert the array/object to JSON. So we'll get a JSON output in the browser. 

It should look like this:

```json
[
    {
        "id": 1,
        "title": "Foo"
    },
    {
        "id": 2,
        "title": "Bar"
    },
    {
        "id": 3,
        "title": "Car"
    },
    {
        "id": 4,
        "title": "Cat"
    },
    {
        "id": 5,
        "title": "PHP"
    }
]
```

Great! You've just made use of a model!

### How it works

First, the model tries to find a table name for itself by looking for a `$table` static property. If doesn't exist then it adds an `s` after the model class name and then converts it into lowercase and sets it as the table name. All kind of operations will use this table name.

Then when the `all()` function is fired, it simply makes a query into the database: `SELECT * FROM posts` and fetches the data using PDO. Then it converts the data into a Collection of Models and returns it.

The `Collection` class implements the `JsonSerializable` Interface, so that it can customize its appearance when it is converted to JSON.