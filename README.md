## Printing object value after deleting it

```javascript
const obj = {
  lang: "js"
};
let x = Object.create(obj);
delete x.lang;
console.log(x.lang) // "js"
```

## Explanation

> This is beacause of the act of "Object.create" it stores the values of the object in the prototype (__proto__) and the delete keyword does not delete anything from the prototype (__proto__)

---

## Printing undefined instead of error

```javascript
console.log(x) // undefined

var x = 10;
```

## Explanation

> This is called [hoisting](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting) this code will be compiled and be like this 
> ```javascript
> var x;
>
> console.log(x) // undefined
>
> x = 10;
> ```
> This only works with var keyword and does not work for let and const, so make that in mind. this works also with functions for example
> ```javascript
> sayHello();
>
> function sayHello() {
> console.log("Hello, World!")
> }
> ```
