# Creating and Understanding a Basic Controller

All of the controllers are placed at `app/Http/Controllers/` directory. The controller class name should have the word `Controller` after its name. For example, `DogController.php`, `CatController.php`... etc, and it should extend the `OSN\Framework\Core\Controller` class.

The methods inside of a controller are generally known as `actions`. These actions contain specific logic for processing data and rendering a view.

A basic controller template should look like this:

```php
<?php

namespace App\Http\Controllers;

use OSN\Framework\Core\Controller;

class FooController extends Controller {
    public function index()
    {
        // code...
    }
}
```

Basically you'll need this template each time when you create a new controller. But with Invention, you can make use of the `Console` by running `php console make:controller FooController` at the top directory of your project. This will create a new file inside the `app/Http/Controllers/` directory and the file will contain the basic template like above. This will speed up your work!