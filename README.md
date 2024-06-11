## :link: Printing object value after deleting it

```javascript
const obj = {
  lang: "js"
};
let x = Object.create(obj);
delete x.lang;
console.log(x.lang) // "js"
```

## Explanation

> This is beacause of the act of "Object.create" it stores the values of the object in the prototype (__proto__) and the delete keyword does not delete anything from the prototype (__proto__).

---

## :link: Printing undefined instead of error

```javascript
console.log(x) // undefined

var x = 10;
```

## Explanation

> This is called [hoisting](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting) this code will be compiled and be like this.
> ```javascript
> var x;
>
> console.log(x) // undefined
>
> x = 10;
> ```
> 
> This only works with var keyword and does not work for let and const, so make that in mind. this works also with functions for example.
> 
> ```javascript
> sayHello();
>
> function sayHello() {
>   console.log("Hello, World!")
> }
> ```

---

## :link: Making function call itself

```javascript
(function (lang) {
  console.log(`Hello, ${lang}!`)
})("javascript") // Hello, javascript!
```

## Explanation

> Yes you can do this. this is called [IIFE](https://developer.mozilla.org/en-US/docs/Glossary/IIFE) it stands for immediately invoked function expression.

---

## :link: Use === instead of ==

```javascript
[10] ===  10      // is false
[10] ==   10      // is true
'10' ==   10      // is true
'10' ===  10      // is false
 []  ==   0       // is true
 []  ===  0       // is false
 ''  ==   false   // is true
 ''  ===  false   // is false 
```

## Explanation

> The == (or !=) operator performs an automatic type conversion if needed. The === (or !==) operator will not perform any conversion. It compares the value and the type, which could be considered faster than ==.

---

## :link: typeof javascript

```javascript
console.log(typeof 1) // number
console.log(typeof NaN) // number
console.log(typeof Infinity) // number
console.log(typeof 1.003) // number
console.log(typeof "1") // string
console.log(typeof false) // boolean
console.log(typeof {}) // object
console.log(typeof []) // object
console.log(typeof null) // object
console.log(typeof new Set()) // object
console.log(typeof __proto__) // function
console.log(typeof function () {}) // function
console.log(typeof class {}) // function
console.log(typeof constructor) // function
console.log(typeof window) // undefined
```

---

## :link: Return trick

```javascript
function f1() {
  return {
    bar: "Hello"
  }
}

function f2() {
  return
  {
    bar: "Hello"
  }
}

console.log(f1()); // {bar: "Hello"}
console.log(f2()); // undefined
```

## Explanation 

> This is beacause of the semi colon that js compiler add at the end of the line, so it will be unreachable code. for example ...
> ```javascript
> function f1() {
>  return 
>  {
>    bar: "Hello"
>  }
> }
> ```
>
> Will be ...
> ```javascript
> function f1() {
>  return;
>  {
>    bar: "Hello"
>  }
> }
> ```

---

## :link: setTimeout order

```javascript
function orders() {
  console.log(1);
  setTimeout(() => console.log(2), 1000);
  setTimeout(() => console.log(3), 0);
  console.log(4);
}

orders() // 1, 4, 3, 2
```

## Explanation

> The console.log executes first before the async functions (setTimout function) and then the async functions executes appending on who is the faster.

## Switch values by destructuring 

```javascript
let x = 5;
let y = 10;

[x, y] = [y, x];

console.log(x, y) // 10, 5
```

## Explanation

> Destructuring is very useful, this example is the same as :
> ```javascript
> let x = 5;
> let y = 10;
> let z;
> 
> z = x;
> x = y;
> y = z;
>
> console.log(x, y) // 10, 5
> ```

## min > max

```javascript
console.log(Math.min() > Math.max()) // true
```

## Explanation

> this is becuase Math.min() function prints Infinity when there is no parameters passed to be ensure that if any parameter passed it will certainly be smaller than Infinity meanwhile Math.max() function prints -Infinity if no parameters passed to be ensure that if any parameter passed it will certainly be greater than -Infinity, so you are likely printing Infinity > -Infinity that is true.
> ```javascript
> console.log(Math.min()) // Infinity
> console.log(Math.max()) // -Infinity
> ```
