# Creating and Understanding a Basic Controller

All of the controllers are placed at `app/Http/Controllers/` directory. The controller class name should have the word `Controller` after its name. For example, `DogController`, `CatController`... etc, and it should extend the `OSN\Framework\Core\Controller` class.

The methods inside of a controller are generally known as `actions`. These actions contain specific logic for processing data and rendering a view.

A basic controller template should look like this:

```php
<?php

namespace App\Http\Controllers;

use OSN\Framework\Core\Controller;

class FooController extends Controller 
{
    public function index()
    {
        // code...
    }
}
```

Basically you'll need this template each time when you create a new controller. But with Invention, you can make use of the `Console` by running `php console make:controller FooController` at the top directory of your project. This will create a new file inside the `app/Http/Controllers/` directory and the file will contain the basic template like above. This will speed up your work!

### Registering a controller

OK, so now we have our first controller; it's time to register it! Open the `routes/web.php` file and add the following line:

```php
Route::get('/foo', [\App\Http\Controllers\FooController::class, 'index']);
```

As you can see, instead of passing a closure to the `get()` method, we've passed an array which has the controller class name at index 0 and the method name at index 1. now this simply means that "Call the index method on FooController whenever a GET request is made on /test".

### More about controllers

There are generally two type of controllers: API and Resource/Web. The API controllers are minimalistic and optimized for JSON data. The Resource controllers are for humans; these are optimized for managing a resource in a user-friendly way.<br>
You can have more methods/actions and register them in the routes. The method naming is fully depending on you, but there is a list of standards for the controller method names and the route paths, which is recommended to follow. The list is given below: (In this list, we've used `/foo` as base route)

##### For the Resource Controllers 

HTTP Method|Route            |Action Method
-----------|-----------------|-------------
`GET`      |`/foo`           |`index()`
`GET`      |`/foo/(\d+)`     |`view($id)`
`GET`      |`/foo/create`    |`create()`
`POST`     |`/foo`           |`store($id)`
`GET`      |`/foo/(\d+)/edit`|`edit($id)`
`PUT`      |`/foo/(\d+)`     |`update($id)`
`PATCH`    |`/foo/(\d+)`     |`update($id)`
`DELETE`   |`/foo/(\d+)`     |`delete($id)`

##### For the API Controllers 

HTTP Method|Route            |Action Method
-----------|-----------------|-------------
`GET`      |`/foo`           |`index()`
`GET`      |`/foo/(\d+)`     |`view($id)`
`POST`     |`/foo`           |`store($id)`
`PUT`      |`/foo/(\d+)`     |`update($id)`
`PATCH`    |`/foo/(\d+)`     |`update($id)`
`DELETE`   |`/foo/(\d+)`     |`delete($id)`

Each of these action methods are explained [here](../action_methods_and_their_work/).<br>
Now, if you follow the above naming conventions, then you get an advantage. Instead of registering all of the methods one-by-one, you can directly use one of `Route::assignAPIController($path, $controller)` and `Route::assignWebController($path, $controller)`.<br>
The `assignAPIController()` registers all applicable routes for an APi controller; and the `assignWebController()` registers routes for a resource controller.