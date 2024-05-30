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
var t3 = [...t2, ...t1];     #spread
console.log(t3);
```

## LOOPS

### FOR LOOP

3 types of for loops

```js
const marks = [80, 30, 40, 23, 45];
for (let i = 0; i < marks.length; i = i + 2) {
  console.log("index", i, "marks", marks[i]);
}
//readable and simple
for (let idx in marks) {
  console.log("Index: ", idx, "marks:", marks[idx]);
}
//readable and cleaner can use when we dont want index
for (let mark of marks) {
  console.log("Mark:", mark);
}
```

### exercise 1

```js
const cart = [
  { name: "A", price: 0.5, qty: 4 },
  { name: "B", price: 0.25, qty: 2 },
];
const new1 = [
  { name: "c", price: 0.35, qty: 2 },
  { name: "D", price: 1.0, qty: 5 },
];
const new2 = [...cart, ...new1];
sum = 0;
for (let item of new2) {
  // for (let i = 0; i < new2.length; i = i + 1) {
  sum = sum + new2[i].price * new2[i].qty;
  //
}
console.log(sum);

//output total price of all products
```

###

### exercise3

```js
const employes = [
  { id: 1, name: "Alice", grade: 78 },
  { id: 2, name: "Bob", grade: 85 },
  { id: 3, name: "Charlie", grade: 92 },
  { id: 4, name: "David", grade: 88 },
  { id: 5, name: "Eva", grade: 76 },
];
var x = [];
for (let i = 0; i < employes.length; i++) {
  if (employes[i].grade > 80) {
    x.push({ id: employes[i].id, status: "promoted" });
  }
}
console.log(x);
// output: [{ id: 2, status: 'Promoted' }, { id: 3, status: 'Promoted' }, { id: 4, status: 'Promoted' }]
```

```js
const movies = [
  { title: "Inception", ratings: [5, 4, 5, 4, 5] },
  { title: "Interstellar", ratings: [5, 5, 4, 5, 4] },
  { title: "Dunkirk", ratings: [4, 4, 4, 3, 4] },
  { title: "The Dark Knight", ratings: [5, 5, 5, 5, 5] },
  { title: "Memento", ratings: [4, 5, 4, 5, 4] },
];
x = [];

function summ(array) {
  var sum = 0;
  for (let i = 0; i < array.length; i++) {
    sum = sum + array[i];
  }
  return sum;
}
for (let i = 0; i < movies.length; i++) {
  x.push(movies[i].ratings);
}
for (let i = 0; i < x.length; i++) {
  x[i] = summ(x[i]);
}
var max = 0;
var index = 0;
for (let i = 0; i < x.length; i++) {
  if (max < x[i]) {
    max = x[i];
    index = i;
  }
}
console.log(movies[index].title);
```
