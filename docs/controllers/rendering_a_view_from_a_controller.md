# Rendering a View from a Controller

It is common to render a view from a controller. To do this, you have 3 ways:

Using `$this->render()`:

```php
<?php

namespace App\Http\Controllers;

use OSN\Framework\Core\Controller;

class FooController extends Controller 
{
    public function index()
    {
        return $this->render("foo");
    }
}
```


Using `view()`:

```php
<?php

namespace App\Http\Controllers;

use OSN\Framework\Core\Controller;

class FooController extends Controller 
{
    public function index()
    {
        return view("foo");
    }
}
```


Using `new View()`:

```php
<?php

namespace App\Http\Controllers;

use OSN\Framework\Core\Controller;
use OSN\Framework\View\View;

class FooController extends Controller 
{
    public function index()
    {
        return new View("foo");
    }
}
```

### Naming the views

There is no rule for naming views that you must follow, but there are some standards that you can follow to enhance your code.

1. You should keep all views relating to a controller within a separate folder. The folder name should match the controller's name (after removing the word Controller and then converting it into lowercase) and should be in snake case. For example, in the above code, the controller is named `FooController`, the views relating to it will go to the folder `foo`.
2. The view names should match the controller's action name and should be in snake case. For example, in the above code, the only action is named `index` in `FooController`, the view for this action will be named `index`.