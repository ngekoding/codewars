# Reverse or rotate?

[Link to the problem](https://www.codewars.com/kata/56b5afb4ed1f6d5fb0000991)

PHP:

```php
function revRot($s, $sz) {
  $len = strlen($s);
  if (empty($s) OR $sz <= 0 OR $sz > $len) return '';
  
  $unused_len = $len % $sz;
  $s = $unused_len > 0 ? substr($s, 0, -1 * $unused_len) : $s;
  $len = strlen($s);
  
  for ($i = 0; $i < $len / $sz; $i++) {
    $arr[] = str_split(substr($s, $i * $sz, $sz));
  }
  
  foreach ($arr as &$a) {
    if (array_sum($a) % 2 == 0) {
      $a = array_reverse($a);
    } else {
      $first = array_shift($a);
      $a[] = $first;
    }
  }
  
  return array_reduce($arr, function($r, $item) {
    return $r.implode('', $item);
  });
}
```
