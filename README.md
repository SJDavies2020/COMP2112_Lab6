# AWAIT

## Introduction

The await expression causes async function execution to pause until a Promise is settled, 
that is fulfilled or rejected, and to resume execution of the async function after fulfillment.
When resumed, the value of the await expression is that of the fulfilled Promise.

If the Promise is rejected, the await expression throws the rejected value.

If the value of the expression following the await operator is not a Promise, 
it's converted to a resolved Promise.

An await can split execution flow, allowing the caller of the await's function to resume execution
before the deferred continuation of the await's function. After the await defers the continuation of its function,
if this is the first await executed by the function, immediate execution also continues by returning to the function's 
caller a pending Promise for the completion of the await's function and resuming execution of that caller.

The array.reduce method takes an array of items and returns a single item,
based on the logic contained in the provided function. The reduce method operates similar to an accumulating for loop, 
by cycling through each item, applying an operation on them, and keeping track of an accumulator throughout the process.
<br>

MDN documentation: [AWAIT MDN docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await)
<hr />

## Example

```javascript

//If a Promise is passed to an await expression, it waits for the Promise to be fulfilled and returns the fulfilled value.

function resolveAfter2Seconds(x) { 
  return new Promise(resolve => {
    setTimeout(() => {
      resolve(x);
    }, 2000);
  });
}

async function f1() {
  var x = await resolveAfter2Seconds(10);
  console.log(x); // 10
}

f1();
```
## Result:

!Fullfilled
