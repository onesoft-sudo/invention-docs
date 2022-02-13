# PowerParser Directive: `:title():`

This directive is generally used in [Layouts](../layouts/). This directive tells PowerParser that get the title specified in the views, and create a variable `$_title` with that value. Then it can be used in the layout to set the page title.

<div class="alert alert-primary">
    <span class="icon info-icon"></span>

    Using multiple `:title():` statements will overwrite the variable `$_title`.
</div>

### Syntax

```php
:title(page_title):
```

### Example

Layout `layouts/app.power.php`
```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>{{ $_title }}</title>
</head>
<body>
  <div class="container">
    :yield('body'):
  </div>
</body>
</html>
```

View:

```php
:extends('layouts.app'):
:title("Login - MyApp"):

:section('body'):
<p>Body</p>
:endsection:
```

This will output:

```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Login - MyApp</title>
</head>
<body>
  <div class="container">
    <p>Body</p>
  </div>
</body>
</html>
```