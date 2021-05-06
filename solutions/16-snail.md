# Snail

[Link to the problem](https://www.codewars.com/kata/521c2db8ddc89b9b7a0000c1)

JavaScript:

```js
snail = function(array) {
  if (!array.length || !array[0].length) return [];
  if (array.length == 1) return array[0];
  
  const results = [];
  const len = array.length;
  const isEven = len % 2 == 0;
  
  let first = 0;
  let end = len - 1;
  
  while (true) {
    for (let i = first; i <= end; i++) {
      if (i == first) {
        let top = array[first].slice(first, end + 1);
        results.push(...top);
      } else if (i == end) {
        let bottom = array[end].slice(first, end + 1).reverse();
        results.push(...bottom);
      } else {
        results.push(array[i][end]);
      }
    }
    
    if (first != end - 1) {
      for (let i = end - 1; i > first; i--) {
        results.push(array[i][first]);
      }
    }
    
    if ((isEven && first == end - 1) || (!isEven && first == end - 2)) {
      break;
    }
    
    first++;
    end--;
  }
  
  if (!isEven) {
    results.push(array[first+1][first+1]);
  }
  
  return results;
}
```
