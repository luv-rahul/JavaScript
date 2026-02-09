# JavaScript Full Course - Part 2

## The DOM (Document Object Model)

- Document Object Model

### Selecting Elements

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <h1 id="abcd">Hi, JavaScript</h1>
    <script src="script.js"></script>
  </body>
</html>
```

```js
let abcd = document.getElementById("abcd");
console.dir(abcd);
```

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <h1 class="abcd">Hi, JavaScript</h1>
    <script src="script.js"></script>
  </body>
</html>
```

```js
let abcd = document.getElementsByClassName("abcd");
console.dir(abcd);
```

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <h1 class="abcd">Hi, JavaScript</h1>
    <script src="script.js"></script>
  </body>
</html>
```

```js
let abcd = document.querySelector("h1");
console.dir(abcd);
```

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <h1 class="abcd">Hi, JavaScript</h1>
    <h1 class="abcd">Hi, JavaScript</h1>
    <h1 class="abcd">Hi, JavaScript</h1>
    <script src="script.js"></script>
  </body>
</html>
```

```js
let abcd = document.querySelectorAll("h1");
console.dir(abcd);
```

### Text / Content Access

```js
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    <h1 class="abcd">Hi, JavaScript</h1>
    <script src="script.js"></script>
</body>

</html>
```

```js
let h1 = document.querySelector("h1");
console.dir(h1);

h1.textContent = "Hello, Rahul";
h1.innerText = "Hello!!";
h1.innerHTML = "<i>Hey!</i>";
```

### Attribute Manipulation

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <a href="http://localhost:5500">Open</a>
    <img src="" alt="" />
    <script src="script.js"></script>
  </body>
</html>
```

```js
let a = document.querySelector("a");
a.href = "https://www.google.com/";
a.setAttribute("href", "https://www.facebook.com/");

let img = document.querySelector("img");

img.setAttribute(
  "src",
  "https://images.unsplash.com/photo-1583121274602-3e2820c69888?w=900&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8M3x8Q2Fyc3xlbnwwfHwwfHx8MA%3D%3D",
);

console.log(a.getAttribute("href"));
img.removeAttribute("src");
```

### Dynamic DOM Manipulation

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <script src="script.js"></script>
  </body>
</html>
```

```js
let h1 = document.createElement("h1");

h1.innerText = "Hello, Bhai!";

// document.body.appendChild(h1);
document.body.prepend(h1);
console.log(h1);

h1.remove();
```

### Style Updates

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <h1>Hello JavaScript</h1>
    <script src="script.js"></script>
  </body>
</html>
```

```js
let h1 = document.querySelector("h1");

h1.style.color = "red";
h1.style.fontFamily = "montserrat";
console.dir(h1.style);

h1.classList.add("hulu");
h1.classList.toggle("hulu");
```
