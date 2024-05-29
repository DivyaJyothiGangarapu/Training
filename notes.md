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
string

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

if the array is declared as const, then also we can change the value inside the value,

```
const t1={1,2,3,4}
const t2=t1
#t2 will be assigned to the initial address of t1
#if we do t1.push(6) and t2.push(9), both t1 and t2 are equal. t1=t2={1,2,3,4,6,9}
```
