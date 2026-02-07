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
