# JavaScript Notes
## Transpiler
`Transpiler` keyword do words se milkar bana hai, `Trans` means `Translation` and `Piler` means `Compiler`. Jese, `Babel` ek javascript transpiler hai, jo source-code ko plain and old ES5 javascript me convert karta hai, taki wo kisi bhi browser me chal sake.

## SetTimeout v/s Sleep
Agar hum python me sleep() function ka use karte hain to jab tak wo function execute nahi ho jata tab tak python next tasks ko execute nahi karta. Lekin, javascript me agar hum setTimeout() function ka use karte hain to jab tak ye function execute hota hai tab tak js next task execute karta hai.
#### Python
``` python
import time
for i in range(1,10):
  time.sleep(1)
  print ('hello')
print (123)
```
output = iss code me sabse pehle python 1 second ke liye wait karega aur uske baad code execute karega lekin jab tak ye code execute nahi ho jata tab tak wo aage nhi badhega aur pehle 1-1 second ke break me 9 baar hello print krega aur uske baad 123 print karega.
#### JavaScript
``` JavaScript
var i = 0;
while (i < 10){
    setTimeout(function(){
      console.log('hello');
      },1000);
  i++;
}
console.log(123);
```
output = iss code me sabse pehle js dekhega ki setTimeout() function ke liye use time lagega, isliye wo uska wait nahi karega aur 123 print kar dega, aur 1-1 second me hello print karta rahega.

## Brackets v/s Spaces
Python me hum indentation use karte hain jisse hume pata chalta hai ki konsa code kis condition ke andar exist karta hai, jese 
``` python
for i in range(1,5):
  print ('hello')
```
yaha par humne print statement me ek indent space diya hai, jisse ye pata chalta hai ki print statement for loop ke andar exist karti hai aur ise python samajh pata hai
Lekin, JavaScript me aisa nahi hota hai. Js curly braces (blocks) ko samajhta hai, e.g.
```javascript
for (var i = 1; i < 5; i++){
  console.log('hello')
}
console.log('hi')
```
yaha par {} se hume pata chalta hai ki 'console.log('hello')' for loop ke andar hai. Yaha indentation ka koi role nahi hai, fir bhi hum indentation lagate hain taki hum uss code ko samajh saken. But, javascript sirf curly braces ko samajhta hai.

## SemiColons (;)
Python me semicolons ka koi role nahi hota hai, aur Enter key press karne par hame uss line ka ending point pata chalta hai.
``` python
print (123)
print (345)
```
output = yaha humne print(123) ke baad humne enter press kiya jisse ki hum next line me pahuch jaaye. Uske baad humne ek fresh line me print (345) likha hai. Aisa hum single line me nahi kar skte.

Lekin javascript me semicolons se uss code ki line ka ending-point pata chalta hai.
``` javascript
console.log(123); console.log(345);
```
output = yaha humne console.log(123) ke baad semicolon ka use karke uss statement ko end kiya hai, aur usi line me hi ek fresh statement likha hai, jabki aisa python me nahi kar skte.

## Variables : 
Python me variables ko declare karne ke liye ushme kishi keyword ka use nahi karna padhta hai 
``` Python
myVar = 20
Name = "Python"
```
jabki javascript me kishi bhi variable ko declare karne se pahle ushko `var` keyword se define karna padhta hai jaise, 
``` javascript 
var myVar = 20; 
var Name = "Javascript";
```

## Data Types
Python ke data types - str (for string values), int (for non-decimal integer values) , boolean, float, list, dict etc.
isme kisi variable ka data type check krne ke liye `type()` function ka use karte hain, e.g. 
```python
a = 12
print (type(a)) #int
b = True
print (type(b)) #boolean
```
JavaScript ke data types - str(for strings), number(for int and float), boolean, array, object (for dictionary), undefined, null, etc.
isme kisi variable ka data type check karne ke liye `typeof()` function ka use karte hain, e.g.
``` javascript
var a = 12; 
console.log(typeof(a)) //number
var b = true;
console.log(typeof(b)) //boolean
```

## If-Else Statement
Python me if-else condition ko likhne ke liye braces ki jarurat nahi hoti hai jaise,
``` Python
if 5<20:
  print(true)
elif 5==20:
  print(false)
else:
  print(false)
```
ishme hum koi bhi statement ko condition ke andar likhne ke liye hum indentation ka use karte hai and condition ko collon(:) se end karte hai. python me `and , or , not ` operators ka use "`and , or , not/!`" aise karte hai. 

Jabki Javascript me `if-else` ke conditions ko braces () ke andar likhte hai and ushke andar statements ko {} ke andar likhte hai and ishme `elif` condition ko `else if` likhte hai.
``` javascript
if (5<20){
  console.log(true);
  }else if (5==20){
  console.log(false);
  }else{
  console.log(false);
  }
```
javascript me `and == && , or == || , not == !` in operators ka use aise karte hai.

## Arrays v/s List :
Python me `List` hota hai and javascript me `Array` hota hai. and dono me `List` and `Array` ko likhne ka syntex same hota hai.
e.g.
``` python
python_list = [1,2,3,['a','b','c'],5,6,7]
var js_array = [1,2,3,['a','b','c'],5,6,7];
```
Python me aur javascript me kuch functions/methods jo dono me bas syntex different hote hai. e.g.
#### python :
``` python
python_list.append(67)  #To insert some element into the list
python_list.pop()  #To remove the last element from the list

len(python_list)  #To check the length of the list.
if (2 in python_list):  #To check the presence of an element in the list. if true then return true otherwise gives false as output.
etc.
```
#### javascript :
``` javascript
js_array.push(67)  //To insert some element into the array.
js_array.pop()  //To remove the last element from the array.
js_array.splice(2,1)  //To remove the 2nd index from the array.

js_array.length  //To check the length of the array or the count of elements in the array.
js_array.indexof(2)  //To check if the element exist in the array and it gives the output in positive index, otherwise gives -1 as output.
```


## Loops
#### while loop:
python and javascript me while loop ka syntex same hota hai.

#### for loop:
python me for loop me `range()` function ka use kar sakte hai jabki javascript me nahi kar sakte hai ishme variable declarartion, conditional statement and increment for loop ke ander hota hai. e.g.

#### python
``` python
for i in range (1,10):
  print(i)
```
#### javascript 
``` javascript
for(var i=1; i<10; i++){
console.log(i);
}
```

## Functions 
Python me function ko `def` keyword se initialize karte hai jabki javascript me `function` keyword ka use karte hai.
e.g.
#### python
``` python
def myFun(name):
  return 'Hello ' + name
print(myFun("python"))
```
#### javascript
``` javascript
function myFun(name){
  return "Hello " + name;
}
console.log(myFun("Javascript"));
```

## Dictionaries v/s Objects 
python me `Dictionary` and javascript me `Object` same cheej hota hai. inka syntax bhi same hota hai.
Python me dictionary ke kishi bhi key ki value ko call karne ke liye hum indexing use karte hai.
e.g.
``` python
Book = {'name' : "Book of fundamentals",
        'year' : 1956
        }
print (Book['name'])  # Book of fundamentals
```
Javascript me object ki kisihi bhi key ki value ko call karne ke liye hum indexing and dot(.) ka bhi use kar sakte hai.
e.g.
``` javascript
var Book = {'name' : "Book of fundamentals",
        'year' : 1956
        }
console.log(Book['name'])  // Book of fundamentals
console.log(Book.year)  // 1956
```

## Random
#### python
Python me `random` ko access karne ke liye `import random` karna padhta hai uske baad uske functions ka hum use kar sakte hai
e.g.
``` python
import random
a=random.random()
print(a)  # prints a random number between 0 and 1.
```
#### Javascript
Javascript me `Math.random()` ka use karte hai 
``` javascript 
var a = Math.random();
console.log(a);  //prints a random number between 0 and 1.
```

## ES6
ECMAScript is a standardized version of JavaScript with the goal of unifying the language's specifications and features. As all major browsers and JavaScript-runtimes follow this specification, the term ECMAScript is interchangeable with the term JavaScript.
JavaScript is an evolving programming language. As features are added and revisions are made, new versions of the language are released for use by developers.

The most recent standardized version is called ECMAScript 6 (ES6), released in 2015. This new version of the language adds some powerful features that will be covered in this section of challenges, including
``` javascript
=> Arrow functions
=> Classes
=> Modules
=> Promises
=> Generators
=> let and const
```
#### Arrow function
``` javascript 
var name = () => {
console.log("hello");
}
```
