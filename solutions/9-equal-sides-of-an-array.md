# Equal Sides Of An Array

[Link to the problem](https://www.codewars.com/kata/5679aa472b8f57fb8c000047)

PHP:

```php
function find_even_index($arr){
  $index = -1;
  $sum = array_sum($arr);
  $length = count($arr);
  
  for ($i = 0; $i < $length; $i++) {
    // We just need to array sum & slice the left side for efficiency
    $sum_left = $i == 0 ? 0 : array_sum(array_slice($arr, 0, $i));
    $sum_right = $i == $length - 1 ? 0 : $sum - $sum_left - $arr[$i];
    
    if ($sum_left == $sum_right) {
      $index = $i;
      break;
    }
  }
  
  return $index;
}
```
