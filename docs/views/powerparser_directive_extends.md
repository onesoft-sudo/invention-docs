# PowerParser Directive: `:extends():`

This directive finds a view or layout with the given name/path and includes it to the current [view](../intro_to_the_views/).

### Syntax

```php
:extends(view_file):
```

### Example

View

```html
:extends('layouts.base'):
:title('Users Page'):

:section('main'):
<h1>Users</h1>
<ul>
    <li>User 1</li>
    <li>User 2</li>
    <li>User 3</li>
</ul>
:endsection:
```

Layout:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{{ $_title }}</title>
</head>
<body>
    :yield('main'):
</body>
</html>
```

Output:

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Users Page</title>
</head>
<body>
    <h1>Users</h1>
    <ul>
        <li>User 1</li>
        <li>User 2</li>
        <li>User 3</li>
    </ul>
</body>
</html>
```