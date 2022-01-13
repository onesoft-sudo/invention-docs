# Creating a new route

First of all, open `routes/web.php` file and add this code:

```php
Route::get("/my-page", function(){
    return "Hello world!";
});
```

This will create a new route and whenever a `GET` request is made on `/my-page` the callback function will be fired; and its return value `Hello world!` will be outputted.

Congratulations! You've created your first route!