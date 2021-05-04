# Bouncing Balls

[Link to the problem](https://www.codewars.com/kata/5544c7a5cb454edb3c000047)

PHP:

```php
function bouncingBall($h, $bounce, $window) {
  if ($h < 1 OR $bounce <= 0 OR $bounce >= 1 OR $window >= $h) return -1;
  
  $c = 1;
  do {
    $h *= $bounce;
    if ($h > $window) {
      $c += 2;
    }
  } while($h > $window);
  
  return $c;
}
```
