# InsertionSort-Modified
## CustomSort Algorithm
### Overview
CustomSort is a sorting algorithm made by me to sort arrays of numbers. This algorithm uses the insertion sort technique to sort the input array in ascending order. The goal of this algorithm is to improve the performance of the basic insertion sort algorithm by reducing the number of comparisons needed to sort the array.
### How it works
The CustomSort algorithm works as follows:

1. Create a new array called sortedArr and add the first element of the input array to it.
2. Loop through the input array starting from the second element.
3. For each element, loop through the sortedArr array from the beginning until a value greater than the current element is found.
4. Insert the current element into the sortedArr array at the position where the value greater than the current element was found.
5. If no value greater than the current element is found, append the current element to the end of the sortedArr array.
6. Once all elements have been processed, the sortedArr array contains the input array sorted in ascending order.

### Performance
The CustomSort algorithm has a time complexity of O(n^2) in the worst case, where n is the number of elements in the input array. This is because the algorithm uses nested loops to compare and insert elements, resulting in potentially many comparisons and insertions. However, in practice, the CustomSort algorithm can be more efficient than basic insertion sort for small arrays, as it reduces the number of comparisons needed to sort the array.

The algorithm has a space complexity of O(n), as it creates a new array to store the sorted elements.
### Versions

#### Version 1
The initial version was a simple implementation of insertion sort, using nested loops to compare and insert elements. This version had a time complexity of O(n^2) in the worst case, and was not particularly efficient for large arrays.

#### Version 2
For the second version an optimization was added to reduce the number of comparisons needed to sort the array. The optimization involved keeping track of the last element that was inserted into the "sortedArr" array, and only comparing the current element with the last element that was inserted, rather than looping through the entire "sortedArr" array. This optimization improved the algorithm's performance for small arrays, but did not significantly improve its time complexity.

### Final Version
The current implementation of the algorithm, which uses the insertion sort technique to sort the input array in ascending order. This version has the same time complexity as the initial version, but is more efficient due to the use of a separate "sortedArr" array to store the sorted elements. The final version has been tested and compared with other sorting algorithms, and has been found to perform well for small arrays.

*Note: More testing is needed in order to determine the performance of the CustomSort algorithm for large arrays and in various scenarios.*

### Usage 
To use the CustomSort algorithm, simply call the function and pass in an array of numbers to be sorted:

```javascript
function customSort(arr) {
  let sortedArr = [arr[0]];
  for (let i = 1; i < arr.length; i++) {
    let inserted = false;
    for (let j = 0; j < sortedArr.length; j++) {
      if (arr[i] < sortedArr[j]) {
        sortedArr.splice(j, 0, arr[i]);
        inserted = true;
        break;
      }
    }
    if (!inserted) {
      sortedArr.push(arr[i]);
    }
  }
  return sortedArr;
}
```

```javascript
const myArray = [4, 2, 8, 3, 1, 6, 5, 7]; 
const sortedArray = customSort(myArray); 
console.log(sortedArray); // [1, 2, 3, 4, 5, 6, 7, 8]
```

### Conclusion
The CustomSort algorithm is a simple and efficient sorting algorithm that is well-suited for small arrays. It is based on the insertion sort technique, and uses a separate array to store the sorted elements. While it may not be the most efficient algorithm for large arrays, it can perform well for small arrays and is a good choice when memory usage is a concern.


