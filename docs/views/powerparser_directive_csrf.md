# PowerParser Directive: `:csrf:`

You can use this directive to attach a hidden input element with a random Cross-Site Request Forgery (CSRF) Token. It has the name of `__csrf_token ` and this authorizes the form to be submitted and the data goes to the controller. If any POST, PUT, PATCH or DELETE request doesn't specify the `__csrf_token` or the `__csrf_token` is invalid, then the request will be rejected with a status of `419 Page Expired`.
This behaviour is controlled by the `VerfyCSRF` middleware which is included with your project.

### Syntax

```php
:csrf:
```

### Example

View

```php
<form action="/users" method="post">
    :csrf:
    <input type="text" name="username">
    <button type="submit" class="btn btn-custom">Submit</button>
</form>
```

Output:

```php
<form action="/users" method="post">
    <input type="hidden" name="__csrf_token" value="f7ff9e8b7bb2e09b70935a5d785e0cc5d9d0abf0">
    <input type="text" name="username">
    <button type="submit" class="btn btn-custom">Submit</button>
</form>
```