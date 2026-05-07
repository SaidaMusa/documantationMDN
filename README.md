# JavaScript Notes

---

## 1. String Case Comparison

```js
const areEqualInUpperCase = (str1, str2) =>
  str1.toUpperCase() === str2.toUpperCase();

const areEqualInLowerCase = (str1, str2) =>
  str1.toLowerCase() === str2.toLowerCase();
````

### Diqqat:

Ba'zi unicode belgilar kutilmagan natija berishi mumkin:

```js
areEqualInUpperCase("ß", "ss"); // true (lekin aslida false bo‘lishi kerak)
areEqualInLowerCase("ı", "I");   // false (lekin true bo‘lishi kerak)
```

---

## 2. Geolocation API

Geolocation API foydalanuvchining joylashuvini olish uchun ishlatiladi (HTTPS talab qiladi).

### getCurrentPosition()

```js
navigator.geolocation.getCurrentPosition(success, error, options);
```

### Parametrlar:

* `success` – muvaffaqiyatli natija callback
* `error` – xatolik callback (ixtiyoriy)
* `options` – sozlamalar (ixtiyoriy)

### options:

```js
{
  maximumAge: 0,            // har safar yangi location
  timeout: 5000,            // kutish vaqti
  enableHighAccuracy: true  // yuqori aniqlik
}
```

---

## 3. watchPosition()

Real-time location kuzatadi.

```js
let id = navigator.geolocation.watchPosition(success, error, options);
navigator.geolocation.clearWatch(id);
```

---

## 4. Geolocation Interfaces

* `Geolocation` – asosiy API
* `GeolocationPosition` – location ma’lumotlari
* `GeolocationPositionError` – xatoliklar

---

## 5. Permissions Policy

```http
Permissions-Policy: geolocation=(self b.example.com)
```

```html
<iframe src="https://b.example.com" allow="geolocation"></iframe>
```

---

## 6. let vs var

### let (block scope)

```js
let x = 1;
if (true) {
  let x = 2;
}
```

### var (function scope)

```js
var x = 1;
if (true) {
  var x = 2;
}
```

---

## 7. delete operator

```js
"use strict";
var x = 1;

delete x; // error in strict mode
```

---

## 8. Bindings

Binding = name + value

```js
let a = 5;
function sum(x, y) {}
```

---

## 9. const

```js
const obj = { name: "Ali" };
obj.name = "Vali"; // mumkin
```

---

## 10. globalThis

Global obyekt:

```js
globalThis.console.log("Hello");
```

---

## 11. Numbers (JS)

* IEEE 754 format
* NaN, Infinity, -Infinity mavjud

### Number literals:

```js
255
0b11111111 // binary
0o377      // octal
0xFF       // hex
```

---

## 12. Math Object

```js
Math.PI
Math.sin(1.56)
Math.random()
Math.floor(4.7)
```

---

## 13. String

### length

```js
"Salom".length // 5
"😊".length    // 2
```

### real character count

```js
[..."😊"].length // 1
```

---

## 14. charAt

```js
"cat".charAt(1) // "a"
"cat"[1]        // "a"
```

---

## 15. String comparison

Unicode asosida ishlaydi:

```js
"a" < "b" // true
```

Case insensitive:

```js
str1.toLowerCase() === str2.toLowerCase()
```

---

## 16. Array

* index 0 dan boshlanadi
* resizable
* mixed types mumkin

```js
let arr = [1, "text", true];
```

---

## 17. Conditional Statements

### if else

```js
if (x > 10) {
} else {
}
```

### ternary

```js
x > 10 ? "big" : "small";
```

---

## 18. switch case

```js
switch (month) {
  case 1:
    console.log("January");
    break;
  default:
    console.log("Unknown");
}
```

---

## 19. Error Handling (Geolocation example)

```js
function error(err) {
  console.log(err.message);
}
```

---

## 20. Summary

* `let` → block scope
* `var` → function scope
* `const` → immutable binding
* JS numbers → IEEE 754
* strings → UTF-16
* geolocation → HTTPS talab qiladi


