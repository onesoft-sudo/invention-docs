# View Components

View components are a special type of views. They can contain some or a lot of HTML widgets such as navbars, lists, buttons..., but the standard is to keep a single widget in a component.
View components are quite handy when you want to use same HTML code in some of your views.

View components are placed at `resources/views/components/` directory. Component files must have the extension `.power.php`.

Let's see a quick example with a simple bootstrap submit button:

Component `components/button.power.php`

```html
<button class="btn btn-primary" type="submit">Submit</button>
```

Now this component can be used in views or layouts; in the following way:

```php
:component("button"):
```

Which means you need to use the `:component:` directive and inside it, you need to pass the base name of the component.
The above code will return the whole content of the component `button.power.php`.

Components can also have argument parameters. You can use arguments in your components in this way:

```php
:args([argument index...]):
```

For example:

Component `components/button.power.php`

```html
<button class="btn btn-primary" type="submit">:args(0):</button>
```

And now you need to use this component with a parameter:

```php
:component("button", "Submit"):
```

Output:

```html
<button class="btn btn-primary" type="submit">Submit</button>
```