# Sodoku Solution Validator

[Link to the problem](https://www.codewars.com/kata/529bf0e9bdf7657179000008)

PHP:

```php
function valid_solution(array $m): bool {
  for ($i = 0; $i < 7; $i += 3) {
    $block = [];
    for ($j = $i; $j <= $i + 2; $j++) {
      for ($k = $i; $k <= $i + 2; $k++) {
        array_push($block, $m[$j][$k]);
      }
    }
    // Checking
    if (in_array(0, $block)) return FALSE;
    if (count(array_unique($block)) < 9) return FALSE;
  }
  return TRUE;
}
```
