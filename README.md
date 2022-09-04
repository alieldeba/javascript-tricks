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

> <p>This is beacause of the act of "Object.create" it stores the values of the object in the prototype (__proto__) and the delete keyword does not delete anything from the prototype (__proto__)</p>
