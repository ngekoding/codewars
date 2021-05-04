# Shortest Word

[Link to the problem](https://www.codewars.com/kata/57cebe1dc6fdc20c57000ac9)

PHP:

```php
function findShort($str){
  $arr = explode(" ", $str);
  usort($arr, function($a, $b) { 
    return strlen($a) <=> strlen($b);
  });
  return strlen($arr[0]);
}
```
