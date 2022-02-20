# More about Routing

You can use PCRE based Regular Expressions in routes to get dynamic values from the request. For example:

```php
Route::get('/foo/(\d+)', function ($id) {
    echo "Number: $id";
});
```

Will call the given closure each time when a GET request is made which matches the PCRE pattern `^/foo/(\d+)$`, and pass the matched values to the closure in the same order.
So, if we make a GET request to `/foo/52`, we'll see `Number: 52` in the browser.

You can have more complex PCRE Patterns as you want but don't forget to use the right order!