# Help the bookseller!

[Link to the problem](https://www.codewars.com/kata/54dc6f5a224c26032800005c)

PHP:

```php
function stockList($listOfArt, $listOfCat){
  if (empty($listOfArt) OR empty($listOfCat)) return '';
  
  // Initial value for all categories
  $results = [];
  foreach ($listOfCat as $cat) {
    $results[$cat] = 0;
  }
  
  // Sum the quantity for each category
  foreach ($listOfArt as $art) {
    list($code, $qty) = explode(' ', $art);
    $cat = $code[0];
    
    if (array_key_exists($cat, $results)) {
      $results[$cat] += $qty;
    }
  }
  
  // Constructing the output format
  $formattedResults = [];
  foreach ($results as $cat => $qty) {
    $formattedResults[] = "($cat : $qty)";
  }
  
  return implode(' - ', $formattedResults);
}
```
