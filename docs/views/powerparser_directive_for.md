# PowerParser Directive: `:for():`

This is equivalent to PHP for loops.

### Syntax

```php
:for(initialization; condition; expression):
<!--HTML or Other PowerParser Directive-->
:endfor:
```

### Example

```php
<ul>
    :for($i = 1; $i <= 5; $i++):
    <li>Page {{ $i }}</li>
    :endfor:
</ul>
```

This will output:

<ul>
    <li>Page 1</li>
    <li>Page 2</li>
    <li>Page 3</li>
    <li>Page 4</li>
    <li>Page 5</li>
</ul>
