# PowerParser Directive: `:yield():`

This directive is generally used in [Layouts](../layouts/). This directive tells PowerParser that find a [Section](../powerparser_directive_section/) which has the same name as given and then output it where the `:yield:` directive is used. You can use multiple `:yield:` directives.

<div class="alert alert-warning">
    <span class="icon alert-icon"></span>

    If a section with the given name doesn't exist then nothing will be outputted.
</div>

### Syntax

```php
:yield(section_name):
```

### Example

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