# PowerParser Directive: `:method():`

You can use this directive to attach a hidden input element with the given HTTP method, and a name of `__method`. This emulates the HTTP method action calling procedure.
The browsers can only send `GET` and `POST` requests, and if you want to use other method rather than `POST`, this directive can be quite handy.

<div class="alert alert-primary">
    <span class="icon info-icon"></span>

    Note that the actual method of the request is always `POST` or `GET`, but the application can understand which method should be triggered from the `__method` field of the request.
</div>

### Syntax

```php
:method(method):
```

### Example

View

```php
<form action="/users" method="post">
    :method("PATCH"):
    :csrf:
    <input type="text" name="username">
    <button type="submit" class="btn btn-custom">Submit</button>
</form>
```

Output:

```php
<form action="/users" method="post">
    <input type="hidden" name="__method" value="PATCH">
    <input type="hidden" name="__csrf_token" value="f7ff9e8b7bb2e09b70935a5d785e0cc5d9d0abf0">
    <input type="text" name="username">
    <button type="submit" class="btn btn-custom">Submit</button>
</form>
```

If we a a route file like this:

```php
Route::get("/users", function(){
    return new View('form');
});

Route::post("/users", function(){
    return 'Handling given data from POST.';
});

Route::patch("/users", function(){
    return 'Handling given data from PATCH.';
});
```

Then after clicking the submit button we should see `Handling given data from PATCH.` in the browser.