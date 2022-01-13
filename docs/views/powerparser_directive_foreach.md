# PowerParser Directive: `:foreach`

This is equivalent to PHP foreach loops.

### Syntax

```php
:foreach($array_or_object as $value)
<!--HTML or Other PowerParser Directive-->
:endforeach
```

or,

```php
:foreach($array_or_object as $key => $value)
<!--HTML or Other PowerParser Directive-->
:endforeach
```

### Example

```php
<ul>
    :foreach($_SERVER as $key => $value)
    <li>{{ $key }} => {{ $value }}</li>
    :endforeach
</ul>
```

This will print out all `$_SERVER` key-value pairs.
