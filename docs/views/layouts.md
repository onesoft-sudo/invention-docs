# Layouts

A layout is a special type of view that can be extended by other views. In short, layouts are the blueprints for the views. Using layouts can make our code less.

If your website has multiple pages, then there is a great chance of having some common HTML code such as header, footer, navbar, copyright text... etc. And you can keep these common code in a single file, which is generally a layout.

Creating a layout is very simple, navigate to `resources/views/layouts/` directory and create a new file `main.php`. Also you can create `main.power.php` if you want to use PowerParser.

Then open the file and add these things if you're not using PowerParser:

```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My First App</title>
</head>
<body>
  [[ view ]]
</body>
</html>
```

Alternatively, add these things if you're using PowerParser:

```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My First App</title>
</head>
<body>
  :yield('content'):
</body>
</html>
```

Then, you need to extend this layout in other views.
Now, in the first case we've used `[[ view ]]` and this tells your app that replace that token with the incoming view content. The `:yield()` directive is almost same as `[[ view ]]`.

If you're not using PowerParser, then you need to open the `config/app.php` file add edit the `layout` field and add the layout path to the field. In this case, it is `layouts/main`. Note that the extensions are not allowed here, just pass the base name.

Then you can create a new view `test.php` and then add some code:

```html
<h1>Hello world!</h1>
<p>Your layout and view(s) are working!</p>
```

And now you can add a test route to the `routes/web.php` file which simply returns a view (In this case it is `test`):

```php
Route::get('/testing-a-view', function(){
    return view('test');
});
```

And hopefully in the browser you should see the title `My First App` which means the layout is working and you should also see other stuff in the view.

Now, if you're using PowerParser, then follow these steps:

Create a new view `test.power.php` (Remember, the extension `.power.php` tells your app that it is a PowerParser file, and `.php` tells you app that it is a simple PHP file.):

```html
:extends('layouts.main'):

:section('content'):
<h1>Hello world!</h1>
<p>Your layout and view(s) are working!</p>
:endsection:
```

And then add a new route as done before.
Now, hopefully you should see the same result.

Both of those views are rendered like this:

```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My First App</title>
</head>
<body>
  <h1>Hello world!</h1>
<p>Your layout and view(s) are working!</p>
</body>
</html>
```