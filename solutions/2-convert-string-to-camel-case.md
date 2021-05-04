# Convert string to camel case

[Link to the problem](https://www.codewars.com/kata/517abf86da9663f1d2000003)

PHP:

```php
function toCamelCase($str){
  $arr = str_split($str);
  $result = '';
  for ($i = 0; $i < count($arr);) {
    if (in_array($arr[$i], ['-', '_'])) {
      $result .= strtoupper($arr[$i+1]);
      $i += 2;
    } else {
      $result .= $arr[$i];
      $i++;
    }
  }
  return $result;
}
```
