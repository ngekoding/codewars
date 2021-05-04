# Tribonacci Sequence

[Link to the problem](https://www.codewars.com/kata/556deca17c58da83c00002db)

PHP:

```php
function tribonacci($signature, $n) {
  if ($n == 0) return [];
  if ($n <= 3) return array_slice($signature, 0, $n);
  
  for ($i = 3; $i < $n; $i++) {
    $signature[] = array_sum(array_slice($signature, $i-3, 3));
  }
  
  return $signature;
}
```
