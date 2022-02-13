# Application & Entry Points

The `public/index.php` file is the entry point of the application; it just creates an instance of the `App` class and calls the `run()` method on it.
This file is always served by the HTTP server (e. g. Apache). Also, there is a `public/.htaccess` file which configures apache to always serve the `index.php` file.

### Understanding how the application works
Whenever an instance of `App` is created, it initializes other application services. This initialization process is done by the `Initializers`. Your application initializers are placed at `app/Initializers`. These initializers generally look like this:

```php
<?php

namespace App\Initializers;


use OSN\Framework\Core\Initializer;

class AppInitializer extends Initializer
{
    /**
     * Before app initialization.
     * Note that some components/objects might not be initialized at this point.
     *
     * @return void
     */
    public function preinit()
    {
        //
    }

    /**
     * Initialize the app.
     *
     * @return void
     */
    public function init()
    {
        //
    }

    /**
     * After app initialization, when the run() method is called.
     *
     * @return void
     */
    public function afterinit()
    {
        //
    }
}
```

The `preinit()` method is called before the application gets ready; the `init()` method is fired when the app is ready and about to boot; the `afterinit()` method is invoked after the `run()` method is called on the application instance.

You can register or configure your application services in those methods.
There are already some Initializers present on your application, but you can create your own if you need.