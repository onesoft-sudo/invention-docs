# Meet PowerParser

PowerParser is a strong, regex-based and excellent templating engine which will make your work and code less.
PowerParser is included with Invention Framework, so you don't need to worry about that.

PowerParser supports a bunch of directives that can make your code elegant and less. If you're familier with [Laravel Framework](https://laravel.com), then you should probably know about [Laravel's Blade Directives](https://laravel.com/docs/8.x/blade), and PowerParser supports almost every directive of Blade!

For example, an `if` statement in Blade:

```php
@if(condition)
<!--HTML-->
@endif
```

But in PowerParser, you need to just replace the `@` with a `:`

```php
:if(condition)
<!--HTML-->
:endif
```

Outputting something:

```php
{{ "text" }}
``` 

```php
{{ $variable }}
``` 

```php
{{ func() }}
``` 

PowerParser will call `htmlspecialchars()` and filter strings every time when you output something in this way.

Also you might need a single line PHP code which should not be outputted, for that use this:

```php
!{{ "Text" }}! <!--Nothing is outputted-->
```

```php
!{{ $variable++ }}! <!--Increments $variable by 1-->
```

```php
!{{ $var = func() }}! <!--Calls func() and assigns the return value to $var--->
```