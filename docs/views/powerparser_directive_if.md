# PowerParser Directive: `:if`

This is equivalent to PHP if statements.

### Simple If Conditions

```php
:if(condition)
<!--HTML or Other PowerParser Directive-->
:endif
```

### If-else Conditions

```php
:if(condition)
<!--HTML or Other PowerParser Directive-->
:else
<!--HTML or Other PowerParser Directive-->
:endif
```

### If-elseif-else Conditions

```php
:if(condition)
<!--HTML or Other PowerParser Directive--> 
:elseif(condition)
<!--HTML or Other PowerParser Directive-->
:elseif(condition)
<!--HTML or Other PowerParser Directive-->
:else
<!--HTML or Other PowerParser Directive-->
:endif
```