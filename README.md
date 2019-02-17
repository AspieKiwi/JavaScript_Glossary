# JavaScript Glossary

## List
Apply( )



## Apply( )
### Syntax
``` JavaScript
function.apply(thisArg, [argsArray])
```
### Parameters
thisArg - Optional. THe value of this provided for the call to func. Note that this may not be the actual value seen by the method: if the method is a function in non-strict mode, null and undefined will be replaced with the global object and primitive values will be boxed.

argsArray - Optional. An array like object, specifying the arguments which func should be called or null or undefined if no arguments should be provided to the function. Starting with ECMAScript 5 these arguments can be a generic array-like object instead of an array.

[Source](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply)

### Description
The first argument in both cases is the value of this that we wish for the call function to have.

Essentially, the only difference between these two methods is the fact that in apply, the second argument is an array object of arguments while in call, all arguments are sent in a common separated format. [Source](https://www.geeksforgeeks.org/arrow-functions-in-javascript/)

The apply( ) method calls a function with a given value and arguments provided as an array (or an array-like object). [Source](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply)

You can assign a differnet this object when calling an existing function. this refers to the current object, the calling object. With apply, you can write a method once and then inherit it in another object, without having to rewrite the method for the new object.

apply is very similar to call( ), except for the type of arguments it supports. You use an arguments array instead of a list of arguments (parameter). With apply, you can also use an array literal, for example, func.apply(this,['eat', 'bananas'] or an Array object, for example, func.apply(this. new Array('eat', 'bananas')).

You can also use arguments for the argsArray parameter. arguments is a local variable of a function. It can be used for all unspecified arguments of the called object. Thus, you do not have to know the arguments of the call object whne you use the apply method. You can use arguments to pass all the arguments to the called object. The called object is then responsible for handling the arguments.

Since ECMAScript 5th Edition you can also use any kind of object which is array-like, so in practice, this means it's going to have a property length and integer properties in the range(0..length-1). As an exapmle you can now use a NodeList or a custom object like {'length':2, '0': 'eat', '1':'bananas'}.

Most browsers, including Chrome and Internet Explorer 9, still do not accept array-like objects and will throw an exception.

[Source](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply)


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










