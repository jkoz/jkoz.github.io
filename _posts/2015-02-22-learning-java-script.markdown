---
layout: post
---

## Introduction

- Java & Javascript does not related

- Rules: style sheet should be loaded first in a html file and java script should be loaded at bottom of body.

- Go to console tab of firebug in Firefox, and enable script area enter following tests (like python)

## Conditions

```javascript

// if conditions
// == equality
// === strict equality, check type also
var a = 5
var b = "5"
if (a == b) {
    alert("They're equal")
}
if (a !== b) {
    alert("They're NOT strictly equal")
}
if (a === b && a === 5) {
    alert("And operators")

}
```

## Operators

```javascript
// incr and decr, postfix and prefix
a += 1;
a++;
alert(++a);

// ternary operator, console.log() only seen by developers
a > 8 ? console.log('true') : console.log(" less than 8")

```

## Loops

```javascript

// loops
var a = 1;
while (a < 3) {
    console.log(a);
    a++;
}

// at least run one
var a = 10
do {
    console.log(a);
    a++;
} while (a < 3)

// for 
for (var i = 1; i < 100; i++) {
    if (i == 6) {
        break;
    }
    if (i % 5 === 0) {
        continue; // done with this iteration
    }
    console.log(i)
}

```

## Functions

```javascript

// functions
function myFunc(x, y) {
    console.log("Calculate sum of ")
    console.log(x)
    return x + y;
}
myFunc(a, b);
var ret = myFunc(1, 2);
console.log(ret);

// extra parameters, interpreter will ignore the surpluses
var ret = myFunc(1, 2, 21, 2 ,31);
console.log(ret);

// missing parameters will be considered as 'undefined'
var ret = myFunc();
console.log(ret);

```

## Arrays

```javascript
// array
var arr = [];
arr[0] = 50;
arr[1] = 60;
arr[2] = "Mouse"
console.log(arr)

var arr2 = [ 1, 2, "Mouse" ]
console.log(arr2)

var arr3 = new Array();
var arr4 = Array();

// Array methods and properties: length, reverse(), sort(), join()
console.log(arr4.length);
arr4[0] = 123
console.log(arr4.length);

// list all a tag in document
var myArrayOflinks = document.getElementsByTagName("a")

```

## Numbers 

```javascript
// Numbers: all javascript numbers are 64b floating point numbers
var foo = 5;
var bar = "b";
console.log(foo + bar); // to string "55"
console.log(foo * bar); // NaN - not a number

// isNaN
var foo = "55"
var n = Number(foo)
if (!isNaN(n)) { // if NOT NOT a number
    console.log("It is a number!");
}

// Math functions: round(), max(), min(), random(), sqrt()
var y = Math.round(200.4)

```

## String

```Javascript
// String properties and methods: toUpperCase(), split(), indexOf(), slice(), substring(), substr()

// String compare
var str1="hello";
var str2="Hello";
if (str1.toLowerCase() == str2.toLowerCase()) {
    console.log("Equal")
}

// ABC.. less than acbd... is True
// Google for more: "Mozilla Javascript references"

```
## Dates

```javascript

// Date methods and properties
var today = new Date();
console.log(today);
console.log(today.getMonth()); // 0 is January
console.log("Grace was born on", today.getDay()); // 0 is sunday

// Compare date
var date1 = new Date(2000, 0, 1);
var date2 = new Date(2000, 0, 1);
// not if (date1 == date2)
if (date1.getTime() == date2.getTime()) {
    console.log("equal")
}

```

## Objects

```javascript
// Objects: Array, Date, String, Number
// Object properties
// long-hand create object
// There is no official class like others

var player = new Object();
player.name = "Fred"
player.score = 1000;
player.rank = 1;

// shorthand create object
var player1 = { name: "Fred", score: 1000, rank: 1};
console.log(player1.name);

function playerDetails() {
    console.log(this.name + " has a rank of: " + this.rank + " and a score of " + this.score);
}

player.logDetails = playerDetails
player1.logDetails = playerDetails;

player.logDetails();
player1.logDetails();

```

## DOM - Document Object Model

### Element, attribute and text nodes

```html
$ cat /tmp/ttt.html
<html>
    <head>
        <title>A title of my example</title>
    </head>
    <body>
        <div id="mainTitle">
            <ul id="optionList">
                <li>This is the first option</li>
            </ul>
            <a href="asdsa">MyLink1</a>
        </div>
    </body>
    <script src="ttt.js"></script>
</html>
```

- element node: ul, li, p, h1
- attribute node: id="optionList"
- text node: This is the first option

```javascript
$ cat /tmp/ttt.js
var mainTitle = document.getElementById("mainTitle");
console.log("This is an element of type: ", mainTitle.nodeType);
console.log("The Inner HTML is: ", mainTitle.innerHTML);
console.log("Child nodes: ", mainTitle.childNodes);
// get all achor
var myLinks = document.getElementsByTagName("a");
console.log("Links: ", myLinks.length);
```


