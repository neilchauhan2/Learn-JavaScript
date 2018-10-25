

Description:

The javascript forEach method, which was introduced with ECMASCRIPT 3, applies a given callback function to each individual item in an array, in ascending order. 
The callback function is invoked with 3 arguments: value, index and the array being iterated through. However, the function only executes if the array item has a value. For example, to print the contents of an array to console:


    let myArray = ["Hello", "this", "is", "an", "array!"];

    myArray.forEach((item) => console.log(item));

    //or

    myArray.forEach(function(item) {
        console.log(item);
    })
    
    //prints "Hello" 
             "this" 
             "is" 
             "an" 
             "array!" to the console.