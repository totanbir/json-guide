## Welcome to Json-Example
JSON (JavaScript Object Notation) is a lightweight data-interchange format. It is easy for humans to read and write. It is easy for machines to parse and generate.

## Comments
---
Single line comments start with `//json`. For multi-line commands `/* json */` or `<!-- json -->` 

## Json Syntax
---
### Json data types:
* a string
* a number
* an object (JSON object)
* an array
* a boolean
* null

### Json number types:
* Integer
* Fraction
* Exponent

### Json Objects:
```js
{
"developer":{ "name":"Rafi", "age":20, "city":"Barisal" }
}
```
### Json Array:
```js
{
"developer":[ "Rafi", "Dhaka", "Bangladesh" ]
}
```
### Json Strings:
```js
{ "name":"Rafi" }
```
### Json Numbers:
```js
{ "year": 2017 }
```
### Json Booleans:
```js
{ "name": true }
```
### Json Null:
```js
{ "name": null }
```
### Example showing array containing multiple objects:
```js
{
   "devlopers": [
      { "name":"nahid" , "skill":"laravel" },
      { "name":"rid" , "skill":"php" },
      { "name":"rafi" , "skill":"html" }
   ]
}
```
## Json Objects
---
### Json Object Syntax:
```js
{ "name":"rafi", "age":10, "class":null, "year": true }
```
### Json Accessing Object Values:
```js
obj = { "name":"rafi", "age":10, "class":null, "year": true };
myobj= obj.name;
```
or
```js
obj = { "name":"rafi", "age":10, "class":null, "year": true };
myobj= obj["name"];
```
### Json Looping Object:
```js
loopobj = { "name":"rafi", "age":10, "class":null, "year": true };
for (x in loopobj) {
    document.getElementById("demo").innerHTML += x;
}
```
or
```js
loopobj = { "name":"rafi", "age":10, "class":null, "year": true };
for (x in loopobj) {
    document.getElementById("demo").innerHTML += loopobj[x];
}
```
### Json Nested Objects:
```js
Nesobj = {
    "name":"nahid",
    "age":30,
    "skill": {
        "skill1":"laravel",
        "skill2":"php",
        "skill3":"js",
        "skill4":"vue.js"
    }
 }
 ```
> Access nested Json objects
```js
 x = nesobj.skill.skill3;
```
or
```js
x = nesobj.skill["skill3"];
```
## Json Arrays
---
### Arrays in Json Objects:
```js
arrobj = {
"name":"Rafi",
"phone":01723xxxxxx,
"address": "Dhaka, Bangladesh",
"skill":[ "php", "html", "css", "javascript" ]
}
```
> Access Array Values
```js
x = arrobj.skill[0];
```
### Json Looping array:
```js
for (i in arrobj.skill) {
    x += arrobj.skill[i];
}
```
or
```js
for (i = 0; i < arrobj.skill.length; i++) {
    x += arrobj.skill[i];
}
```
### Json Nested arrays:
