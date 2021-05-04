# Are they the "same"?

[Link to the problem](https://www.codewars.com/kata/550498447451fbbd7600041c)

PHP:

```php
function comp($a1, $a2) {
  if (
    $a1 === NULL OR $a2 === NULL OR 
    count($a1) != count($a2)
  ) return FALSE;
  
  $useds = [];
  foreach ($a1 as $v1) {
    $pow = pow($v1, 2);
    $found = FALSE;
    foreach ($a2 as $key => $v2) {
      if ($pow == $v2 && !in_array($key, $useds)) {
        $found = TRUE;
        array_push($useds, $key);
        break;
      }
    }
    if ($found === FALSE) return FALSE;
  }
  
  return TRUE;
}
```
