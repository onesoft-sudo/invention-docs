# PowerParser Directive: `:while():`

This is equivalent to PHP while loops.

### Syntax

```php
:while(condition):
<!--HTML or Other PowerParser Directive-->
:endwhile:
```

### Example

```php
<ul>
    !{{ $i = 1 }}!
    :while($i <= 5):
    <li>Page {{ $i }}</li>
    !{{ $i++ }}!
    :endwhile:
</ul>
```

This will output:

```html
<ul>
    <li>Page 1</li>
    <li>Page 2</li>
    <li>Page 3</li>
    <li>Page 4</li>
    <li>Page 5</li>
</ul>
```
