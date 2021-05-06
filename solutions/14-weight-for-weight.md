# Weight for weight

[Link to the problem](https://www.codewars.com/kata/55c6126177c9441a570000cc)

PHP:

```php
function orderWeight($str) {
  $str = trim($str);
  $arr = explode(' ', $str);
  usort($arr, function($a, $b) {
    $valA = array_sum(str_split($a));
    $valB = array_sum(str_split($b));
    
    if ($valA == $valB) return strcmp($a, $b);
    return $valA <=> $valB;
  });
  return implode(' ', $arr);
}
```
