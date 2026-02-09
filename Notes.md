# 📚 JavaScript - Full Course | Sheriyans Coding School

## 🔤 Variables and Declarations

> Variables are data storage memory location.

---

## 📦 Variable Types

### **`var`**

**Window Object**

- It adds in window object.

```js
var a = 10;
undefined;

window;
GetParams: ƒ(e);
a: 10;
```

**Function Scope**

```js
function abcd() {
  if (true) {
    var a = 10; // var is available to function scope
  }
  console.log(a);
}

abcd();

// 10
```

**Re-declaration**

- It can be re-declared, with same name and it won't give error.

```js
var a = 10;
var a = 20;
```

---

### **`let`**

**Window Object**

- It doesn't add in window object.

```js
let a = 10;
undefined

window
GetParams: ƒ (e)
...
```

**Block Scope**

```js
function abcd() {
  if (true) {
    let a = 10; // let is available to block scope
  }
  console.log(a);
}

abcd(); // a is not defined
```

**Modification**

- It can be modified, but not re-declared.

```js
let a = 10;
a = 20;
// Works fine!

let a = 10;
let a = 20;

// Cannot redeclare block-scoped variable 'a'.
```

---

### **`const`**

**Window Object**

- It doesn't add in window object.

```js
const a = 10;
undefined

window
GetParams: ƒ (e)
...
```

**Block Scope**

```js
function abcd() {
  if (true) {
    const a = 10; // const is available to block scope
  }
  console.log(a);
}

abcd(); // a is not defined
```

**Immutability**

- It can't neither be modified nor re-declared.

```js
const a = 10;
a = 20;
// Assignment to constant variable.

const a = 10;
const a = 20;

// Cannot redeclare block-scoped variable 'a'.
```

---

## 🎯 Key Concepts

### **Declarations**

```js
var a;
let a;
const a;
```

### **Initialization**

```js
var a = 10;
let a = 10;
const a = 10;
```

### **Re-Initialization**

```js
var a = 10;
var a = 20; // It works!

let a = 10;
let a = 20; // Error

const a = 10;
const a = 20; // Error
```

---

## 🌍 Scope

**Types of Scope:**

- Global Scope
- Block Scope
- Function Scope

### **Global Scope Example**

```js
var a = 10;

{
  var a = 20;
  console.log(a); // var is not inside function, so it has global scope.
}
```

### **Block Scope Example**

```js
let a = 10;

function abcd() {
  if (true) {
    let b = 10;
  }

  console.log(a); // 10 .Since let is global scoped (BTS: Whole code is wrapped inside function (block scope of outermost function) for JS engine to execute it), so accessible here.
  console.log(b); // ReferenceError: b is not defined. Block Scope!!
}

abcd();
```

### **Function Scope Example**

```js
function abcd() {
  if (true) {
    var a = 10; // var is available to function scope
  }
  console.log(a);
}

abcd();

// 10
```

---

## ⏰ Temporal Dead Zone

**TDZ = declaration se pehle ka time, jahan variable exist karta hai but usable nahi hota**

```js
console.log(a);
// ReferenceError: a is not defined
```

```js
console.log(a);

let a = 5;

// Cannot access 'a' before initialization
```

It means, JS knows about 'a' at line 3 but doesn't give access to the value.
We can access value only after it is initialized/declared.

This is known as temporal dead zone.

---

## 🚀 Hoisting

**Hoisting = Whenever variables are declared they break into two pieces, fist one is declarations part and second one is initialization.**

Declaration part goes at the top of the program and Initialization part remains at its place.

**Hoisting Behavior:**

- `var` → Hoist → `undefined`
- `let` → Hoist → ❌ (TDZ)
- `const` → Hoist → ❌ (TDZ)

### **Example with `var`**

```js
console.log(a);

var a = 10;
// var a = undefined; // moves up
// a = 10; // remains at it's place
```

It actually happens like this:

```js
var a = undefined;
console.log(a); // undefined

a = 10;
```

**Note:** In case of var, ouput is undefined, but in case of let and const, they also get hoisted but, they are in temporal dead zone (Can't access value before initialization), so we got !!REFERENCE ERROR!!.

### **Example with `let`**

```js
console.log(a); // ReferenceError: Cannot access 'a' before initialization

let a = 5;
```

---

## 📊 Quick Reference Table

| Feature       | `var`       | `let`  | `const` |
| ------------- | ----------- | ------ | ------- |
| Window Object | ✅ Yes      | ❌ No  | ❌ No   |
| Scope         | Function    | Block  | Block   |
| Re-declare    | ✅ Yes      | ❌ No  | ❌ No   |
| Re-assign     | ✅ Yes      | ✅ Yes | ❌ No   |
| Hoisting      | `undefined` | TDZ    | TDZ     |

## DataTypes + Type System

1. Primitives

- All those values, on copying them we get real copy of it.
- e.g. string, number, boolean, null, undefined

```js
let a = 10; // a = 10
let b = a; // b = 10
```

**string**

- 'data' // single quotes
- "data" // double quotes
- `data` // back ticks

```js
let name = "Rahul";
```

**number**

- 0,1,2,3,4,5...
- -1,-2,-3,-4,-5...
- 1.2,3.51 etc.

```js
let a = 10;
```

**bool**
true / false

```js
let isLive = true;
```

**null**
If we want explicitly to not give value to a variable, we can give it null.

```js
let a = null;
```

**undefined**
If the variable is not assigned, any value, by default, it's value is undefined.

```js
let a;

a; // undefined
```

2. Reference

- On copying these values, we don't get copy, we get reference of parent
- e.g. arrays, objects, functions

```js
let a = [1, 2, 3];
let b = a; // [1,2,3]
b.pop(); // [1,2]

a; // [1,2]
```

## Arrays

**Create**

```js
let arr = [];
```

**Initialize**

```js
let marks = [10, 20, 30, 40, 50];
```

**Access**

```js
console.log(marks[0]);
console.log(marks[1]);
console.log(marks[2]);
console.log(marks[3]);
console.log(marks[4]);
console.log(marks[5]);
```

**Modify**

```js
marks[0] = 100;
console.log(marks[0]);
```

**Array Methods**

1. push

```js
let arr = [10, 20, 30, 40, 50];

/**
 * push method:
 * - Insert element at last of an array
 * - Returns length of new array
 */
let a = arr.push(100);

console.log(arr);
console.log(a);

// [10, 20, 30, 40, 50, 100]
// 6
```

2. pop

```js
let arr = [10, 20, 30, 40, 50];

/**
 * push method:
 * - Removes element at last of an array
 * - Returns removed element of array
 * - Array is empty - Returns Undefined
 */
let a = arr.pop(10);

console.log(arr);
console.log(a);

// [10, 20, 30, 40]
// 50
```

3. shift

```js
let arr = [10, 20, 30, 40, 50];

/**
 * push method:
 * - Removes element at start of an array
 * - Returns removed element of array
 * - Array is empty - Returns Undefined
 */
let a = arr.pop(10);

console.log(arr);
console.log(a);

// [20, 30, 40, 50]
// 50
```

4. unshift

```js
// Inserts new elements at the start of an array, and returns the new length of the array.

let a = arr.unshift(10);

console.log(arr);
console.log(a);

// [10, 10, 20, 30, 40, 50]
// 6
```

5. splice

```js
let arr = [10, 20, 30, 40, 50];

/*
 * splice(start: number, deleteCount?: number) */

let a = arr.splice(2, 1);

console.log(arr);
console.log(a);

// [10, 20, 40, 50]
// [30]
```

6. slice

```js
let arr = [10, 20, 30, 40, 50];

let a = arr.slice(1, 2);

/*
 * Returns a copy of a section of an array.
 */

console.log(arr);
console.log(a);

// [10, 20, 30, 40, 50]
// [20]
```

7. reverse

```js
let arr = [10, 20, 30, 40, 50];

let a = arr.reverse();

console.log(arr);
console.log(a);

// [50, 40, 30, 20, 10]
// [50, 40, 30, 20, 10]
```

8. sort

```js
let arr = [10, 20, 30, 40, 50];

/*
 * Sorts an array in place. This method mutates the array and returns a reference to the same array.
 * NOTE: Sort default works on making values as string then sort.
 * If we want the  sorting on numbers, we need to use extra function passed into it.
 */

let a = arr.sort((a, b) => b - a);

console.log(arr);
console.log(a);

// [50, 40, 30, 20, 10]
// [50, 40, 30, 20, 10]
```

9. forEach

```js
let arr = [10, 20, 30, 40, 50];

/*
 * Performs the specified action for each element in an array.
 * !Returns nothing
 */
let a = arr.forEach((val) => {
  console.log(val);
});

console.log(arr);
console.log(a);

// 10
// 20
// 30
// 40
// 50
// (5) [10, 20, 30, 40, 50]
// undefined
```

10. map

```js
let arr = [10, 20, 30, 40, 50];

/*
 * - It always return an  new array.
 * - The value inside the new array can be undefined, if not meeting condition.
 */

let a = arr.map((val) => {
  console.log(val);
});

console.log(arr);
console.log(a);

// 10
// 20
// 30
// 40
// 50
// (5) [10, 20, 30, 40, 50]
// (5) [undefined, undefined, undefined, undefined, undefined]
```

```js
let arr = [10, 20, 30, 40, 50];

let a = arr.map((val) => {
  if (val < 25) {
    return val;
  }
});

console.log(arr);
console.log(a);

// [10, 20, 30, 40, 50]
// (5)[(10, 20, undefined, undefined, undefined)];
```

11. filter

```js
let arr = [10, 20, 30, 40, 50];

/*
 * Returns a new Array based on condition - i.e. true or false
 */

let a = arr.filter((val) => {
  if (val < 25) {
    return val;
  }
});

console.log(arr);
console.log(a);

// (5) [10, 20, 30, 40, 50]
// (2) [10, 20]
```

12. reduce

```js
/*
 * When we want to reduce the array to a single value, then we use it.
 */
let arr = [10, 20, 30, 40, 50];

let a = arr.reduce((accumulator, val) => {
  return accumulator + val;
}, 0);

console.log(arr);
console.log(a);

// (5) [10, 20, 30, 40, 50]
// 150
```

13. find

```js
Returns the value of the first element in the array where predicate is true, and undefined otherwise.

let arr = [11, 67, 3, 4, 25];

let a = arr.find((val) => val > 50);

console.log(arr);
console.log(a);

// (5) [11, 67, 3, 4, 25]
// 67
```

14. some

```js
let arr = [11, 67, 3, 4, 25];

/*
 * OR Operator Behaviour
 * This is used to check whether any element of the array satisfies the given function.
 * If any one will be true, then returns true.
 */

let a = arr.some((val) => val > 50);

console.log(arr);
console.log(a);

// (5) [11, 67, 3, 4, 25]
// true
```

15. every

```js
let arr = [11, 67, 3, 4, 25];
/*
 * AND Operator
 * This is used to check whether every element of the array satisfies the given function.
 * If any one will be true, then returns true.
 */

let a = arr.every((val) => val > 50);

console.log(arr);
console.log(a);

// (5) [11, 67, 3, 4, 25]
// false
```

**Array Destructuring**

```js
let arr = [11, 67, 3, 4, 25];

let [a, b, , c] = arr;
console.log(arr);
console.log(a);
console.log(b);
console.log(c);

// (5) [11, 67, 3, 4, 25]
// 11
// 67
// 4
```

**Spread Operator**

```js
let arr = [11, 67, 3, 4, 25];

/*
 * When we need to copy array to another, we use this. In below example, the array is copied but as a reference.
 * Changes in new array will lead to changes in original array.
 */

let brr = arr;
brr[0] = 100;

// arr
// (5) [100, 67, 3, 4, 25]
// brr
// (5) [100, 67, 3, 4, 25]
```

```js
let arr = [11, 67, 3, 4, 25];

let brr = [...arr];
brr[0] = 100;

// arr
// (5) [11, 67, 3, 4, 25]
// brr
// (5) [100, 67, 3, 4, 25]
```

## Objects

It is a structure in which we store data in form of key-value.

**Key-Value**

```js
key: value;
```

**Dot & Bracket Notation**

```js
let obj = {
  name: "Rahul",
  age: 24,
};

// obj.name;
// ("Rahul");
// obj.age;
// 24;
// obj["name"];
// ("Rahul");
// obj["age"];
// 24;
```

**Nesting and Deep Access**

```js
let obj = {
  name: "Rahul",
  age: 24,
  address: {
    city: "Delhi",
    location: {
      lat: 28.7041,
      long: 77.1025,
    },
  },
};

obj.address.location.lat;
28.7041;
```

**Object Destructuring**

```js
let obj = {
  name: "Rahul",
  age: 24,
  address: {
    city: "Delhi",
    location: {
      lat: 28.7041,
      long: 77.1025,
    },
  },
};

const { lat, long } = obj.address.location;
console.log(lat);
console.log(long);

let newObj = {
  "first-name": "Rahul",
};

const { "first-name": firstName } = newObj;
console.log(firstName);

// 28.7041
// 77.1025
// Rahul
```

**for-in, Object.keys, Object.entries**

```js
let obj = {
  name: "Rahul",
  age: 24,
  address: {
    city: "Delhi",
    location: {
      lat: 28.7041,
      long: 77.1025,
    },
  },
};

for (let key in obj) {
  console.log(key, obj[key]);
}

// name Rahul
//  age 24
//  address {city: 'Delhi', location: {…}}
```

```js
let obj = {
  name: "Rahul",
  age: 24,
  address: {
    city: "Delhi",
    location: {
      lat: 28.7041,
      long: 77.1025,
    },
  },
};

// Object.keys(obj);
// (3)[("name", "age", "address")];
```

````js
let obj = {
  name: "Rahul",
  age: 24,
  address: {
    city: "Delhi",
    location: {
      lat: 28.7041,
      long: 77.1025,
    },
  },
};


Object.entries(obj);
(3) [Array(2), Array(2), Array(2)]0: (2) ['name', 'Rahul']1: (2) ['age', 24]2: (2) ['address', {…}]```
````

**Spread Operator - Shallow Copy**

- For nested-structure, spread operator copies the structure into another object but as reference.

- Changes in new object reflect in original object.

- To avoid

```js
let obj = {
  name: "Rahul",
  age: 24,
  address: {
    city: "Delhi",
    location: {
      lat: 28.7041,
      long: 77.1025,
    },
  },
};

let obj2 = { ...obj };

// obj2.address.city = "Shimla"
// 'Shimla'
// obj.address.city
// 'Shimla'
```

**Deep Clone/ Deep Copy**

```js
let obj = {
  name: "Rahul",
  age: 24,
  address: {
    city: "Delhi",
    location: {
      lat: 28.7041,
      long: 77.1025,
    },
  },
};

let obj2 = JSON.parse(JSON.stringify(obj));

// obj2.address.city = "Shimla"
// 'Shimla'
// obj.address.city
// 'Delhi'
```

**Optional Chaining**

```js
let obj = {
  name: "Rahul",
  age: 24,
  address: {
    city: "Delhi",
    location: {
      lat: 28.7041,
      long: 77.1025,
    },
  },
};

console.log(obj?.address?.city); // Delhi
```

**Computed Properties: Key-Value**

```js
let key = "role";

let obj = {
  name: "Rahul",
  age: 24,
  address: {
    city: "Delhi",
    location: {
      lat: 28.7041,
      long: 77.1025,
    },
  },
  [key]: "admin",
};
```
