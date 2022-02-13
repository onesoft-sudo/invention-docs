# PowerParser Directive: `:args():`

This directive finds an argument with the given index and outputs it. This directive is only available in [components](../view_components/);

### Syntax

```php
:args(argument_index):
```

### Example

View

```php
:component('some-component', 'Arg1', 'Arg2', 'Last Arg'):
```

Component:

```php
<p>:args(0):</p>
<p>:args(1):</p>
<p>:args(2):</p>
```

Output:

```php
<p>Arg1</p>
<p>Arg2</p>
<p>Last Arg</p>
```