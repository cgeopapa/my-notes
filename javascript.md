# Javascript

## Lexical Scope

The scope we all know and love

## Function Expresions

```javascript
var foo = function bar() {...};

foo(); //ok
bar(); //error
```

`bar` does not exist in global scope

## IIFE

```javascript
var foo = "foo";

(function(){
    var foo = "foo2";
    console.log(foo); //"foo2"

})();

console.log(foo); // "foo"
```

Same as opening and closing {} in other normal language

### loops

```javascript
for (var i=1; i <=5; i++){
    (function(i){
        setTimeout(function(){
            console.log(i);
        }, i * 1000);
    })(i);
}
```

Here each iteration has its own i.

## let & var

```javascript
function foo()
{
    for (let i = 0; i < 10; i++)
    {
        console.log(i);
    }
    console.log(i); //error
}
```

```javascript
function foo()
{
    for (var i = 0; i < 10; i++)
    {
        console.log(i);
    }
    console.log(i); //10
}
```

`let` is the one we all know and love. It scopes in the block which is inside. `var` goes to the scope\(function or global\).

## hoisting

```javascript
var a = b();
var c = d();
a;
c;

function b(){
    return c;
}

var d = function(){
    return b();
}
```

Javascript runs a compiling phase first where it declares all variables and functions. It then goes ahead and asign values according to the assignments. So in line 1 even though function b\(\) is declared later there is no error whatsoever.

## this Keyword

FORGET CLASSES! 1. Was the function called with `new`? 2. Was the function called with `call` or `apply` specifying an explicit `this`? 3. Was the function called via a containing object? 4. If in strict mode bind to undefined, else to the global scope.

## Closure

```javascript
function foo(){
    var bar = "bar";

    function baz(){
        console.log(bar);
    }
    bam(baz);
}

function bam(baz){
    baz();  // "bar"
}
foo();
```

## Modules

```javascript
var foo = (function(){
    var publicAPI = {
        bar: function(){
            publicAPI.baz();
        },
        baz: function(){
            console.log("baz");
        }
    };
    return publicAPI;
})();

foo.bar();  //"baz"
```

So now foo is like a class object with private members.

