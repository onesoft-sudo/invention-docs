# Return Values of a Controller Action

A controller action can return one of the following types:

- `string`
- `int`
- `bool`
- `array`
- `object`
- `\JsonSerializable`
- `\OSN\Framework\View\View`
- `\OSN\Framework\Core\Response`

So basically you can return everything except `null`.