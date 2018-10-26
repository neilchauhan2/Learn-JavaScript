# Promises

JavaScript is a single-threaded, but handles many operations through asynchronous callbacks.  While providing for a fairly powerful programming model, they can also be very difficult to read and maintain.  Take the following example.

```JavaScript
// Take a set of 2 functions myAsyncFunction and myAsyncFunction2 that both execute callbacks when done.
myAsyncFunction(function (err, result) => {
  if (!err) {
    myAsyncFunction2(function (err, result) => {
      if (!err) {
        console.log('asynchronous processing done!')
      }
      else {
        handleError(err)
    }
 }
 else {
  handleError(err)
 }
}
```
This is what is often called Christmas-tree code, as we nest more and more callbacks the shape begins to look just like a Christmas tree.  Difficult to read, debug, and maintain.  There are ways, however, to mitigate this somewhat by declaring the callback functions independently and then passing them into the async functions as args, but this still makes the code look somewhat disjointed.

Promises seek to solve this by providing a way to declare the handling of callbacks in a more sequential form like so

```JavaScript
// Taking two functions, myPromiseFunction and myPromiseFunction2, that both return Promises instead

myPromiseFunction()
  .then((result) => myPromiseFunction2(result))
  .then(() => {
    console.log('asynchronous processing done!')
   })
   .catch((err) => {
    handleError(err)
   })

```
