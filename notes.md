# Intro to web development

### JAVA SCRIPT

- ifen=dot

  1.

  - cccc

  2.

## this is a code

```css
center code {
  ......;
}
```

## new file

! +enter

## Linking script file to html file rather than writing the js code

<script src="scope.js"></script>
<script src="hjjb.js"></script>

> highlight

https://developer.mozilla.org/en-US/docs/Web/HTTP/Status

![all http status code](https://udzial.com/wp-content/uploads/2021/04/HTTP-Status-Code-Nmemonics.png) -[image compression](https://squoosh.app/)

#### SVG

Scalable Vector Graphics (SVG) is a web-friendly vector file format. vector-based graphics in XML format.
SVG graphics are scalable, and do not lose any quality if they are zoomed or resized. SVG is supported by all major browsers.

#### continous integration and continous deployement CICD

## INTRO TO JAVA SCRIPT

variabe

```java script
var x=10
typeof(x)
```

#### data types

number(4,4.5),  
strings("x","divya"),  
boolean,  
string,  
object  
undefined

```javascript
var student={
  name:"divya",
  marks:40
}
console.log(student.name);         #divya
console.log(student["marks"]);     #40
typeof(student)                #object


var marks=[10,20,30,40]
typeof(marks)                  #object
marks[0]                       #10
40/0                           #infinity not error

var t=null
console.log(typeof t);         #object not null
typeof(infinity)               #number

var z;
typeof(z)                      #undefined
```

### Declartions

#### redeclaration,reassignment

Var : redeclaration is allowed,allowed  
let : not allowed,allowed  
const : not allowed,not allowed  
redclaration creating a same variable again,creating a variable with same address.  
reassignment modifying the value of the variable.

if the array is declared as const, then also we can change the value inside the value,

```js
const t1={1,2,3,4}
const t2=t1
#t2 will be assigned to the initial address of t1
#if we do t1.push(6) and t2.push(9), both t1 and t2 are equal. t1=t2={1,2,3,4,6,9}
```

### undefined and not defined

undefined is not a error it is output , when we declare a variable but not assigned any value to it.  
Not defined is an error, occured when we didnt declare a variable and trying to access it

### SCOPE

let , Const --> block scope  
var --> function scope

```js
function driving(age) {
  if (age > 18) {
    var msg = "eligible";
  } else {
    var msg = "not eligible";
  }

  console.log("he is" + msg);
}
driving(20);
```

### type casting

#### implicit

done by the compiler automatically when any operations performed.when JS automatically decides itself.

#### explicit

we manually do the type casting by parseint, toString.

```
var x1 = 2;
var x2 = "g";
console.log(x1 + x2);          #2g it concatinated
console.log(x1 - x2);          #Nan not a number or undefined
```

```
var x1 = 2;
      var x2 = "3";
      console.log(x1 + x2);
      console.log(x1 - x2);
```

adding a array and string

```js
[2,4,5].toString()           #'2,4,5'
[2,4,       5].toString()    #'2,4,5'
[2,4,5]+"abc"                #'2,4,5abc'
[]+[]                        #' '
null+5                       #5
4 * "5a"                     #NaN
NaN/4                        #NaN
typeof(NaN)                  #number
```

### == or === which is faster and y?

=== is faster only one step
== is slower coation (type conversion) and then compares the value which takes much time.

## Functions

if we dont give the return statement ,undefined will be printed  
return: returns value to function call  
arguments: values that are passed in the parameters  
parameters: are the varibles that are defined inside the function.  
function are just to avoid repetition of code.  
DRY- Dont repeat yourself  
modification also becomes easy  
reusability,readability,changes in one place it get reflected in all places.

2 ways to exit a function

1. return statement
2. untill end of the function block

### Arrow Function

```js
const double = (n) => {
  return n * 2;
};
```

if the function is one line, we can write in one line

```js
const double1 = (n) => n * 2;
```

### 5 pillars of code Quality

1. readability-75%
2. Maintainability - Code Debt(i will make the code better tommorrow that day never come)
3. Extensibility
4. Testability
5. Performance

```js
var q1 = [100, 200];
var q2 = [...q1];
var q3 = [60, ...q1, 90, 40];
console.log(q3);
var t1 = [400, 500];
let t2 = [90, 80];
var t3 = [...t2, ...t1];
console.log(t3);
```
