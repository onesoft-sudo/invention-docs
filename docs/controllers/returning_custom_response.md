# Returning Custom Response

To return a custom response, you have these ways:

Using `Response` object:

```php
public function index()
{
    return new \OSN\Framework\Core\Response('', 403);
}
```

Using `response()` function:

```php
public function index()
{
    return response('', 403);
}
```

Both the `Response` contructor and the `response()` function takes the first argument as the response content and the second argument as the status code. Finally you may pass an array of headers to them:


```php
public function index()
{
    return response('', 403, [
        'X-Powered-By' => "Invention+PHP/8.x"
    ]);
}
```