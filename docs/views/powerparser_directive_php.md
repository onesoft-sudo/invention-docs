# PowerParser Directive: `:php:`

You can write plain PHP code inside this directive.

### Syntax

```php
:php:
// php code
:endphp:
```

### Example

```php
<ul>
    :php:
        for($i = 0; $i < 5; $i++) {
            echo "<li>{$i}</li>";
        }
    :endphp:
</ul>
```

This will output:

```html
<ul>
    <li>1</li>
    <li>2</li>
    <li>3</li>
    <li>4</li>
    <li>5</li>
</ul>
```
