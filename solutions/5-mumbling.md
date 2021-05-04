# Mumbling

[Link to the problem](https://www.codewars.com/kata/5667e8f4e3f572a8f2000039)

PHP:

```php
function accum($s) {
  $arr = str_split($s);
  $result = array_map(function($index, $char) {
    return ucfirst(strtolower(str_repeat($char, $index + 1)));
  }, array_keys($arr), $arr);
  return implode('-', $result);
}
```
