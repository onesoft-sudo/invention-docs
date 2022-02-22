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

You can specify folders:

```php
Route::get("/home", function(){
    return new View('test/home');
});
```

Using `.` (dot):

```php
Route::get("/home", function(){
    return new View('test.home'); // same as above
});
```

<div class="alert alert-warning">
    <span class="icon alert-icon"></span>
    If the given view doesn't exist then it will throw a `FileNotFoundException`.
</div>

### Passing data to the views

You can pass an array of data in this way:

```php
Route::get("/home", function(){
    return view('test', [
        'foo' => 'bar',
        'one' => 1
    ]);
});
```

In your view, you can access these data as variables. The variable names will be same as the array keys:

```php
<?= $foo ?>
```