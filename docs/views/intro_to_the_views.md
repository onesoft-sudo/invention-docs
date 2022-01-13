# Intro to the Views

In the route callback function, instead of returning some string, we render a view and then return it.

We can do this using the global `view()` function or return a `View` object:

```php
Route::get("/", function(){
    return view('home');
});

Route::get("/home", function(){
    return new View('home');
});
```

Now this `view()` function or `View` object checks if the `resources/views/` directory contains a view named `[given_name].php` or `[given_name].power.php`; if exists then it returns the whole content of the file as a string. In this case the `[given_name]` is `home`.

<div class="alert alert-warning">
    <span class="alert-icon"></span>
    If the given view doesn't exist then it will throw a `FileNotFoundException`.
</div>