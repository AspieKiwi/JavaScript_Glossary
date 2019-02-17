# JavaScript Glossary

## List
Apply( )



## Apply( )
### Syntax
``` Ruby
function.apply(thisValue, [arg1, arg2, ...])
```

The first argument in both cases is the value of this that we wish for the call function to have.

Essentially, the only difference between these two methods is the fact that in apply, the second argument is an array object of arguments while in call, all arguments are sent in a common separated format.


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

Note: Both call( ) and apply( ) are methods that are available on the prototype of the default function object.

[Source](https://www.geeksforgeeks.org/arrow-functions-in-javascript/)
