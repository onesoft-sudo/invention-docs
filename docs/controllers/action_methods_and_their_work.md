# Action Methods and Their Work

There are some standard controller actions which can be used to enhance your app's code. You're not forced to use these methods, but it is recommended to do so.

### The `index()` method

**Used in**: Resource and API controllers<br>
Displays a listing of the resource.

### The `view()` method

**Used in**: Resource and API controllers<br>
**Arguments**: `$id`<br>
Displays information about a specific resource.

### The `create()` method

**Used in**: Resource controllers<br>
Displays a form for taking required data from the user to create a new resource.

### The `store()` method

**Used in**: Resource and API controllers<br>
**Arguments**: `\OSN\Framework\Core\Request $request`<br>
Creates a brand new resource with the user input.

### The `edit()` method

**Used in**: Resource controllers<br>
**Arguments**: `\OSN\Framework\Core\Request $request, $id`<br>
Displays a form for taking required data from the user to modify an existing resource.


### The `update()` method

**Used in**: Resource and API controllers<br>
**Arguments**: `\OSN\Framework\Core\Request $request, $id`<br>
Updates an existing resource according to the user input.

### The `delete()` method

**Used in**: Resource and API controllers<br>
**Arguments**: `$id`<br>
Deletes an existing resource.