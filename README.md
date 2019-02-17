# JavaScript Glossary

## List
Apply( )



## Apply( )
### Syntax
``` Ruby
function.apply(thisValue, [arg1, arg2, ...])
```

The first argument in both cases is the value of this that we wish for the call function to have.

Essentially, the only difference between these two methods is the fact that in apply, the second argument is an array object of arguments while in call, all arguments are sent in a common separated format. [Source](https://www.geeksforgeeks.org/arrow-functions-in-javascript/)

The apply( ) method calls a function with a given value and arguments provided as an array (or an array-like object). [Source](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply)


### Examples
``` Html
<!DOCTYPE html>
<html>
  <body>
    <script>
      // Create two different objects to test call() and apply()
      let banana = { person : 'Banana' };
      let orange = { person : 'Orange' };
      function fruits(adj)
      {
        document.write(this + ' ');
        return (this.person + " is " + adj + ' ');
      }
      
      // call() and apply() will immediately invoke
      // the function they are being called on
      
      // logs: Banana is yummy
      document.write(fruits.call(banana, 'yummy'));
      
      // logs: Orange is sour
      document.write(fruits.apply(orange, [ 'sour' ]));
    </script>
  </body>
</html>
```

Output

``` Html
[object Object] Banana is yummy
[object Object] Orange is sour
```

[Source](https://www.geeksforgeeks.org/arrow-functions-in-javascript/)



``` JavaScript
var numbers = [5, 6, 2, 3, 7];

var max = Math.max.apply(null, numbers);

console.log(max);
// expected output: 7

var min = Math.min.apply(null, numbers);

console.log(min);
// expected output: 2
```
Output
``` JavaScript
7
2
```

[Source](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply)










