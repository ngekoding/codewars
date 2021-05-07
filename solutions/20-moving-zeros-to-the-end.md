# Moving Zeros To The End

[Link to the problem](https://www.codewars.com/kata/52597aa56021e91c93000cb0)

PHP:

```php
function moveZeros(array $items): array
{
  usort($items, function($a, $b) {
    if ($a === 0 OR $a === 0.0) return 1;
    if ($b === 0 OR $b === 0.0) return -1;
  });
  return $items;
}
```
