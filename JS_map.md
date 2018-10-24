# Map Funtion

## Description
The **_map()_** method is used to apply a function on every element in an array.
A new array is then returned.

## Syntax
Here is how the syntax looks like

```
let newArr = oldArr.map((value, index, array) =>{
	//return element to new Array
});
```
* ```newArr``` - the new array that is returned
* ```oldArr``` - the array to run the map function on
* ```value``` - the current value being processed
* ```index``` - the current index of the value being processed
* ```array``` - the original array

## Example
Here is a example of how to use a map function

```
let myArr = [1,2,3,4];

let newArr = myArr.map((value, index, array) => {
	return value * 2;
});
```

Results

```
console.log(myArr); //[1,2,3,4]
console.log(newArr); //[2,4,6,8]
```
