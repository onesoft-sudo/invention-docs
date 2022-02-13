# PowerParser Directive: `:component():`

This directive parses and outputs a view component.

You can read more about view components [here](../view_components/).


### Syntax

```php
:component(name, [args...]):
```

### Example

Component `component/button.power.php`

```html
<button class="btn btn-primary:args(0):" type=":args(1):">:args(2):</button>
```

View:

```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My First App</title>
</head>
<body>
  <h1>Components</h1>
  <form action="">
    <input type="text">
    :component('button', ' me-2', 'submit', 'Submit'):
    :component('button', ' me-2', 'button', 'Normal Button'):
    :component('button', '', 'reset', 'Reset'):
  </form>
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
  <h1>Components</h1>
  <form action="">
    <input type="text">
    <button class="btn btn-primary me-2" type="submit">Submit</button>
    <button class="btn btn-primary me-2" type="button">Normal Button</button>
    <button class="btn btn-primary" type="reset">Reset</button>
  </form>
</body>
</html>
```