# PowerParser Directive: `:if():`

This is equivalent to PHP if statements.

### Simple If Conditions

```php
:if(condition):
<!--HTML or Other PowerParser Directive-->
:endif:
```

### If-else Conditions

```php
:if(condition):
<!--HTML or Other PowerParser Directive-->
:else:
<!--HTML or Other PowerParser Directive-->
:endif:
```

### If-elseif-else Conditions

```php
:if(condition):
<!--HTML or Other PowerParser Directive--> 
:elseif(condition):
<!--HTML or Other PowerParser Directive-->
:elseif(condition):
<!--HTML or Other PowerParser Directive-->
:else:
<!--HTML or Other PowerParser Directive-->
:endif:
```

### Examples

```php
<div>
    !{{ $i = 1 }}!
    :if($i === 1):
        <p>{{ $i }} is equal to 1</p>
    :endif:
    :if($i === 2):
        <p>{{ $i }} is equal to 2</p>
    :endif:
</div>
```

This will output:

```html
<div>
    <p>1 is equal to 1</p>
</div>
```
<hr>
```php
<div>
    !{{ $i = 2 }}!
    :if($i === 1):
        <p>{{ $i }} is equal to 1</p>
    :else:
        <p>{{ $i }} is not equal to 1</p>
    :endif:
</div>
```

This will output:

```html
<div>
    <p>2 is not equal to 1</p>
</div>
```

<hr>
```php
<div>
    !{{ $i = 2 }}!
    :if($i === 1):
        <p>{{ $i }} is equal to 1</p>
    :elseif($i === 2):
        <p>{{ $i }} is equal to 2</p>
    :else:
        <p>{{ $i }} is not equal to 1 or 2</p>
    :endif:
</div>
```

This will output:

```html
<div>
    <p>2 is equal to 2</p>
</div>
```
