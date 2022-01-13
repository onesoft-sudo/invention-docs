# PowerParser Directive: `:dowhile`

This is equivalent to PHP do-while loops.

### Syntax

```php
:dowhile
<!--HTML or Other PowerParser Directive-->
:enddowhile(condition)
```

### Example

```php
<ul>
    !{{ $i = 1 }}!
    :dowhile
    <li>Page {{ $i }}</li>
    !{{ $i++ }}!
    :enddowhile($i <= 0)
</ul>
```

This will output:

<ul>
    <li>Page 1</li>
</ul>
