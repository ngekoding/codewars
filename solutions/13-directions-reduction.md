# Directions Reduction

[Link to the problem](https://www.codewars.com/kata/550f22f4d758534c1100025a)

PHP:

```php
function dirReduc($arr) {
  $loop = FALSE;
  for ($i = 0; $i < count($arr) - 1; $i++) {
    if (
      ($arr[$i] == 'NORTH' && $arr[$i+1] == 'SOUTH') OR 
      ($arr[$i] == 'SOUTH' && $arr[$i+1] == 'NORTH') OR 
      ($arr[$i] == 'WEST' && $arr[$i+1] == 'EAST') OR 
      ($arr[$i] == 'EAST' && $arr[$i+1] == 'WEST')
    ) {
      unset($arr[$i+1]);
      unset($arr[$i]);
      $loop = TRUE;
    }
  }

  if ($loop) return dirReduc(array_values($arr));
  return $arr;
}
```
