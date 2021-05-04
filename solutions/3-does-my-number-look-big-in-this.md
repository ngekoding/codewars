# Does my number look big in this?

[Link to the problem](https://www.codewars.com/kata/5287e858c6b5a9678200083c)

PHP:

```php
function narcissistic(int $value): bool {
  $len = strlen(strval($value));
  $sum = array_sum(array_map(function($val) use ($len) {
    return pow($val, $len);
  }, str_split(strval($value))));
  return $value == $sum;
}
```
