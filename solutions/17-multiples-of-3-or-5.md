# Multiples of 3 or 5

[Link to the problem](https://www.codewars.com/kata/514b92a657cdc65150000006)

PHP:

```php
function solution($number){
  $sum = 0;
  for ($i = 1; $i < $number; $i++) {
    if ($i % 3 == 0 OR $i % 5 == 0) {
      $sum += $i;
    }
  }
  return $sum;
}
```