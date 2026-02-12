## getCurrentPosition() is a method which can be found device’s current 
location works with HTTPS websites 
If it is not working at all may be it is blocked by geolocation 
### Permissions-Policy. 
### getCurrentPosition(success) 
### getCurrentPosition(success, error) 
### getCurrentPosition(success, error, options) 
### success 
A callback function that takes a GeolocationPosition object as its sole input parameter. 
error Optional 
An optional callback function that takes a GeolocationPositionError object as its sole 
input parameter. 
options Optional 
### maximumAge 
This is also a good method we can predict device’s milestones, if it is maximumAge 0 ,it asks new location gps all 
the time.If it is more than 0 it will ask only that period for example 5(5000 milesstones) and after that period it will 
give you old gps.if its value is infinity it gives you only older gps locations. 
### Timeout – it is like infinity it gives old location 
### EnableHighAccuracy- it is boolean if it is true it can give you possible locations 

![alt text]({BDDC30D2-0CE4-45F2-B954-909D431C752C}.png)



### watchPosition() method

It is available since 2015 July.That is a handler function which finds eachtime user changes location . We can also error handle with it. We can handle it by ID.It has options,error,success just like getCurrentPosition() function.


let id;
let target;
let options;

function success(pos) {
  const crd = pos.coords;

  if (target.latitude === crd.latitude && target.longitude === crd.longitude) {
    console.log("Congratulations, you reached the target");
    navigator.geolocation.clearWatch(id);
  }
}

function error(err) {
  console.error(`ERROR(${err.code}): ${err.message}`);
}

target = {
  latitude: 0,
  longitude: 0,
};

options = {
  enableHighAccuracy: false,
  timeout: 5000,
  maximumAge: 0,
};

id = navigator.geolocation.watchPosition(success, error, options);



### Interfaces

### Geolocation

It is main class of this API. 

### GeolocationPosition

Represents location of a user.A succesfull call  of method in Geolocation.inside a success callback, and contains a timestamp plus a GeolocationCoordinates object instance.


### GeolocationPositionError

it is also error notifier


The Geolocation API allows users to programmatically access location information in secure contexts.
Access may further be controlled by the Permissions Policy directive geolocation. The default allowlist for geolocation is self, which allows access to location information in same-origin nested frames only. Third party usage is enabled by setting a Permissions-Policy response header to grant permission to a particular third party origin:

### http


Permissions-Policy: geolocation=(self b.example.com)

The allow="geolocation" attribute must then be added to the iframe element with sources from that origin:

### html


<iframe src="https://b.example.com" allow="geolocation"></iframe>

Geolocation data may reveal information that the device owner does not want to share. Therefore, users must grant explicit permission via a prompt when either Geolocation.getCurrentPosition() or Geolocation.watchPosition() is called (unless the permission state is already granted or denied). The lifetime of a granted permission depends on the user agent, and may be time based, session based, or even permanent. The Permissions API geolocation permission can be used to test whether access to use location information is granted, denied or prompt (requires user acknowledgement of a prompt).

A GeolocationPositionError is returned by an unsuccessful call to one of the methods contained inside Geolocation, inside an error callback, and contains an error code and message.

### variables 

### let 

The let declaration declares re-assignable, block-scoped local variables, optionally initializing each to a value.Let is confirmed and used since 2016

let x = 1;

if (x === 1) {
  let x = 2;

  console.log(x);
  // Expected output: 2
}

console.log(x);
// Expected output: 1


let name1;
let name1 = value1;
let name1 = value1, name2 = value2;
let name1, name2 = value2;
let name1 = value1, name2, /* …, */ nameN = valueN;


### var
The var statement declares function-scoped or globally-scoped variables, optionally initializing each to a value.Var is used since 2015 for all browsers.

var x = 1;

if (x === 1) {
  var x = 2;

  console.log(x);
  // Expected output: 2
}

console.log(x);
// Expected output: 2


function foo() {
  var x = 1;
  function bar() {
    var y = 2;
    console.log(x); // 1 (function `bar` closes over `x`)
    console.log(y); // 2 (`y` is in scope)
  }
  bar();
  console.log(x); // 1 (`x` is in scope)
  console.log(y); // ReferenceError, `y` is scoped to `bar`
}

foo();



### for (var a of [1, 2, 3]);
console.log(a); // 3

Above, for cycle is not working so it takes last value of array.


### for (let a of [1, 2, 3]);
console.log(a);

for this value it gives : Reference error

Because var is function scope but let is block scope.

let a lives inside for{} but var lives in whole function.


### delete operator

"use strict";
var x = 1;
Object.hasOwn(globalThis, "x"); // true
delete globalThis.x; // TypeError in strict mode. Fails silently otherwise.
delete x; // SyntaxError in strict mode. Fails silently otherwise.


### Binding - name+value

let a=5 this is binding because we are connecting a to 5. even parametres are also bindings

function sum(x, y) {
  return x + y;
}

x,y are bindings

try {
  throw new Error("xato");
} catch (e) {
  console.log(e);
}
  here e is binding.


 ### this

### new.target   these two are Javascript bindings.


### mutable and immuteble bindings

const a is immuteble binding because we cant change it.but  let,var a are mutable

### but

const obj = { name: "Ali" };
obj.name = "Vali"; // mutable

const is unvariable but we can change the inside value here.It has properties so we can choose and change it.


### const

The const declaration declares block-scoped local variables. The value of a constant can't be changed through reassignment using the assignment operator, but if a constant is an object, its properties can be added, updated, or removed.
const is just like let it is also block-scoped and also it cannot create globalThis.

### globalThis

This feature is published in January 2020.It is a global property where we can call it everywhere(node.js,js and e.t.c)

### Numbers
In JavaScript, numbers are implemented in double-precision 64-bit binary format IEEE 754 (i.e., a number between ±2^−1022 and ±2^+1023, or about ±10^−308 to ±10^+308, with a numeric precision of 53 bits). Integer values up to ±2^53 − 1 can be represented exactly.

In addition to being able to represent floating-point numbers, the number type has three symbolic values: Infinity, -Infinity, and NaN (not-a-number).

See also JavaScript data types and structures for context with other primitive types in JavaScript.

You can use four types of number literals: decimal, binary, octal, and hexadecimal.

### Decimal numbers
Decimal literals can start with a zero (0) followed by another decimal digit, but if all digits after the leading 0 are smaller than 8, the number is interpreted as an octal number. This is considered a legacy syntax, and number literals prefixed with 0, whether interpreted as octal or decimal, cause a syntax error in strict mode — so, use the 0o prefix instead.


0888 // 888 parsed as decimal
0777 // parsed as octal, 511 in decimal


### Binary numbers
Binary number syntax uses a leading zero followed by a lowercase or uppercase Latin letter "B" (0b or 0B). If the digits after the 0b are not 0 or 1, the following SyntaxError is thrown: "Missing binary digits after 0b".


0b10000000000000000000000000000000 // 2147483648
0b01111111100000000000000000000000 // 2139095040
0B00000000011111111111111111111111 // 8388607
Numbers are most commonly expressed in literal forms like 255 or 3.14159. The lexical grammar contains a more detailed reference.


255; // two-hundred and fifty-five
255.0; // same number
255 === 255.0; // true
255 === 0xff; // true (hexadecimal notation)
255 === 0b11111111; // true (binary notation)
255 === 0.255e3; // true (decimal exponential notation)
A number literal like 37 in JavaScript code is a floating-point value, not an integer. There is no separate integer type in common everyday use. (JavaScript also has a BigInt type, but it's not designed to replace Number for everyday uses. 37 is still a number, not a BigInt.)

When used as a function, Number(value) converts a string or other value to the Number type


### Octal numbers
The standard syntax for octal numbers is to prefix them with 0o. For example:


0O755 // 493
0o644 // 420
There's also a legacy syntax for octal numbers — by prefixing the octal number with a zero: 0644 === 420 and "\045" === "%". If the digits after the 0 are outside the range 0 through 7, the number will be interpreted as a decimal number.



### Hexadecimal numbers
Hexadecimal number syntax uses a leading zero followed by a lowercase or uppercase Latin letter "X" (0x or 0X). If the digits after 0x are outside the range (0123456789ABCDEF), the following SyntaxError is thrown: "Identifier starts immediately after numeric literal".


### Numeric separators
For all literal syntaxes shown above, an underscore (_) can be inserted between digits to improve readability.

1_000_000_000_000
1_050.95
0b1010_0001_1000_0101
0o2_2_5_6
0xA0_B0_C0
1_000_000_000_000_000_000_000n





### Math object
The built-in Math object has properties and methods for mathematical constants and functions. For example, the Math object's PI property has the value of pi (3.141…), which you would use in an application as


Math.PI;
Similarly, standard mathematical functions are methods of Math. These include trigonometric, logarithmic, exponential, and other functions. For example, if you want to use the trigonometric function sine, you would write


Math.sin(1.56);
Note that all trigonometric methods of Math take arguments in radians.

The following table summarizes the Math object's methods.

Methods of Math
Method	Description
abs()	Absolute value
sin(), cos(), tan()	Standard trigonometric functions; with the argument in radians.
asin(), acos(), atan(), atan2()	Inverse trigonometric functions; return values in radians.
sinh(), cosh(), tanh()	Hyperbolic functions; argument in hyperbolic angle.
asinh(), acosh(), atanh()	Inverse hyperbolic functions; return values in hyperbolic angle.
pow(), exp(), expm1(), log(), log10(), log1p(), log2()

Exponential and logarithmic functions.
floor(), ceil()	Returns the largest/smallest integer less/greater than or equal to an argument.
min(), max()	Returns the minimum or maximum (respectively) value of a comma separated list of numbers as arguments.
random()	Returns a random number between 0 and 1.
round(), fround(), trunc(),	Rounding and truncation functions.
sqrt(), cbrt(), hypot()	Square root, cube root, Square root of the sum of square arguments.
sign()	The sign of a number, indicating whether the number is positive, negative or zero.
clz32(),
imul()	Number of leading zero bits in the 32-bit binary representation.
The result of the C-like 32-bit multiplication of the two arguments.

In computer programming, a string is a sequence of characters—such as letters, numbers, symbols, or spaces—used to represent text. Strings are treated as a data type, usually enclosed in quotation marks (e.g., "Hello"), and are fundamental for storing and manipulating human-readable text, often immutable in languages.



### String
Baseline Widely available *
This feature is well established and works across many devices and browser versions. It’s been available across browsers since July 2015.

* Some parts of this feature may have varying levels of support.

Learn more
See full compatibility
Report feedback
The String object is used to represent and manipulate a sequence of characters.

In this article
Description
Constructor
Static methods
Instance properties
Instance methods
Examples
Specifications
Browser compatibility
See also
Description
Strings are useful for holding data that can be represented in text form. Some of the most-used operations on strings are to check their length, to build and concatenate them using the + and += string operators, checking for the existence or location of substrings with the indexOf() method, or extracting substrings with the substring() method.

Creating strings
Strings can be created as primitives, from string literals, or as objects, using the String() constructor:

js

Copy
const string1 = "A string primitive";
const string2 = 'Also a string primitive';
const string3 = `Yet another string primitive`;
js

Copy
const string4 = new String("A String object");
String primitives and string objects share many behaviors, but have other important differences and caveats. See "String primitives and String objects" below.

String literals can be specified using single or double quotes, which are treated identically, or using the backtick character `. This last form specifies a template literal: with this form you can interpolate expressions. For more information on the syntax of string literals, see lexical grammar.

Character access
There are two ways to access an individual character in a string. The first is the charAt() method:

js

Copy
"cat".charAt(1); // gives value "a"
The other way is to treat the string as an array-like object, where individual characters correspond to a numerical index:

js

Copy
"cat"[1]; // gives value "a"
When using bracket notation for character access, attempting to delete or assign a value to these properties will not succeed. The properties involved are neither writable nor configurable. (See Object.defineProperty() for more information.)

### eval

Eval is a function which you may add string values

let a = "2+2" // output: "2+2"
let a = eval("2+2") // output: 4
