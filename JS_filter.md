# Filter Function

## Description
The **_filter()_** method is used to filter an array by applying a function to every array entry. If the applied function returns as true, the element is added to the return array. The return value of the method is the filtered array.

## Syntax
Here is how the syntax looks:

```
let filteredArray = arrayToFilter.filter((value, index, array) =>{
	//return element to new Array
});
```
* ```filteredArray``` - The filtered array, which is returned
* ```arrayToFilter``` - The array, which runs the filter function on each element
* ```value``` - The current entry of the array
* ```index``` - The current index of the array entry
* ```array``` - The original array

## Example
Here is an example of how to use a filter function:

```
let arrayToFilter = [1,4,12,13];

let filteredArray = arrayToFilter.filter((value, index, array) => {
	return value % 2 === 1;
});
```

Results

```
console.log(arrayToFilter); // [1,4,12,13]
console.log(filteredArray); // [1, 13]
```