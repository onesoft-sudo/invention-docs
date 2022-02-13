# PowerParser Directive: `:section()::`

Starts an output buffer and saves it, which can be retrived back with an [Yield](../powerparser_directive_yield/) directive.

<div class="alert alert-warning">
    <span class="icon alert-icon"></span>
    
    If multiple sections have the same name, then the last section's output buffer will be returned; because it overwrites the data.
</div>

### Syntax

```php
:section(name):
<!--HTML or Other PowerParser Directive-->
:endsection:
```

### Example

View:

```php
:extends('layouts.app'):

:section('header'):
<h1>Header</h1>
:endsection:

:section('footer'):
<small>Footer</small>
:endsection:

:section('body'):
<p>Body</p>
:endsection:
```

Layout `layouts/app.power.php`
```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My First App</title>
</head>
<body>
  <header>
    :yield('header'):
  </header>
  <main>
    :yield('body'):
  </main>
  <footer>
    :yield('footer'):
  </footer>
</body>
</html>
```


This will output:

```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My First App</title>
</head>
<body>
  <header>
    <h1>Header</h1>
  </header>
  <main>
    <p>Body</p>
  </main>
  <footer>
    <small>Footer</small>
  </footer>
</body>
</html>
```