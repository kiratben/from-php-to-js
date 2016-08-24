# Javascript for PHP Developers
___
The problem when trying to learn a new language is that we consistently learn the basics: variables, functions, conditions ... which can be painful when we already know another programming language. Also, I suggest you use the knowledge you already have PHP in order to accelerate your learning JavaScript.
## Variables
The variables in JavaScript must be declared before being used but it is not necessary to prefix a `$`.
```javascript
var a = 3
a // 3
```
It is also not necessary to terminate our instructions by `;`.

The variables have similar types to those that we know in PHP. However there is no associative arrays. They are "replaced" by objects.
```javascript
var a = 1 // numbers
var b = "string" // No difference between "and '
var c = ['tab', 2, 3.14] // Arrays work like PHP
// Objects "replace" associative arrays
var d = {
    name: 'Lisa',
    note: 18
    notes: [2, 10, 16]    
}
d.name // Lisa 
d['name'] // Lisa
var e = null // null
var f = false // boolean
var g = undefined // No equivalent in PHP
var h //  undefined
```
To concatenate JavaScript do not use the operator`.` but a simple addition.
```javascript
"Hello" + " World" // "Hello World "
//Warning against by the implicit conversion
"3" + 3 // 33
"43" > "7" // false 
43 > 7 // true 
"2" * 2 // 4 (Not possible to multiply a chain, "1" is implicitly converted to a number)
```