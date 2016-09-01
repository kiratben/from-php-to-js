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
## Conditions 
```javascript
if (<condition>) {

} else if (<condition>) { // else if is written in 2 words

} else {

}
```
## Loops
JavaScript supports different kinds of loops:
- for - loops through a block of code a number of times.
- for/in - loops through the properties of an object.
- while - loops through a block of code while a specified condition is true.
- do/while - also loops through a block of code while a specified condition is true.

loops are spelled the same way as PHP.
```javascript
while (<condition>) {

}

for (var i = 0; i < 10; i++) {

}

var person = {fname:"John", lname:"Doe", age:25}; 

var text = "";
var c;
for (c in person) {
    text += person[c];
}
```
In JavaScript there is no foreach loops .

```javascript
// JavaScript alternative to “for each” loop
["Lisa", "Homer", "Bart"].forEach(function (p) {
    "Hello " + p 
})
```
## Functions
The functions can be written as in PHP and are a particular type variable. This will store them in a variable.
```javascript
function func1 (a) {
    return a * 3   
}

var func2 = function (a) {
    return a * 3   
}

func(3) // 9
```

The difference between thesis two ways to declare a function is Explained in the chapter about the hoisting

However there are some differences with PHP

- A function has access to the external environment (external variables to the function in PHP to be used `use()` to get a similar result).
- A function can be called with an incorrect number of parameters, the missing parameters will `undefined`.
- It is not possible to assign a default value to parameters.
- The functions are often used in callback (yet little exploited in PHP)
```javascript
 
var b = "1"
function func (a) {
    return b    
}
func() // "1"
b = 3
func() // 3

// 2. We can call a function without parameters
function func (a) {
    return a    
}
func() // undefined

// 3. If we want to give a default value to the parameter
function func (a) {
    if (a === undefined) {
        a = 0
    }
}
```
### * Everything in JavaScript acts like an object, with the only two exceptions being null and undefined.
```javascript
false.toString(); // 'false'

[1, 2, 3].toString(); // '1,2,3'
["Hello", "Lisa", "World"].length // 3

"Hello".toUpperCase() // "HELLO"
"abc".length // 3

1.123124.toFixed(2) // "1.12"

"1,2,3".split(',') // ['1', '2', '3']

String.fromCharCode(65) // "A"

// JavaScript alternative to “for each” loop
["Lisa", "Homer", "Bart"].forEach(function (p) {
    "Hello " + p 
})
```
This chapter documents all of JavaScript's standard, built-in objects, including their methods and properties [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects).

## OOP in JavaScript
JavaScript is a fully object language that does not share the same logic as PHP. Here I will try to make analogies but be aware that the language does not use classes but rather a heritage based on the prototype system.
```php
class Student {

    private $name;

    public function __construct($name) {
        $this->name = $name;
    }

    public function getName () {
        return $this->name;
    }
}

$bart = new Student('Bart');
```
To translate that into JavaScript must create a constructor.This is done using a simple function.
```javascript
var Student = function (name) {
    this.name = name 
}
var bart = new Student('Bart')
```