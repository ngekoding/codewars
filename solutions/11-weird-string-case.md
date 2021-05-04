# WeIrD StRiNg CaSe

[Link to the problem](https://www.codewars.com/kata/52b757663a95b11b3d00062d)

PHP:

```php
function toWeirdCase($string) {
  $arr = str_split($string);
  $result = '';
  $index = 0;
  foreach ($arr as $c) {
    if ($c == ' ') $index = -1;
    elseif ($index % 2 == 0) $c = strtoupper($c);
    else $c = strtolower($c);
    $result .= $c;
    $index++;
  }
  return $result;
}
```
