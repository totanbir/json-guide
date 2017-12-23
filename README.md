## Welcome to Json-Guide
JSON (JavaScript Object Notation) is a lightweight data-interchange format. It is easy for humans to read and write. It is easy for machines to parse and generate.

## Comments
---
Comments are not Supported in JSON :smiley:

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
"phone":01723*****,
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
```js
nesarr = {
    "name":"Rafi",
    "age":10,
    "year":2017,
    "computer": [
        { "name":"MacBook Pro ", "models":[ "MacBookPro14,1", "MacBookPro14,2", "MacBookPro14,3" ] },
        { "name":"dell", "models":[ "XPS 13", "XPS 15", "XPS 13 2-in-1" ] },
        { "name":"fujitsu", "models":[ "LH-532", "LH-531" ] }
    ]
 }
 ```
 > Access Nested array Values
 ```js
 for (i in nesarr.computer) {
    x += "<p>" + nesarr.computer[i].name + "</p>";
    for (j in nesarr.computer[i].models) {
        x += nesarr.computer[i].models[j];
    }
}
```
### Json Modify array Values:
```js
nesarr.computer[1] = "XPS 17"
```
### Json Delete array:
```js
delete nesarr.computer[1];
```
## Json parse
---
### Json Parsing
```js
'{ "name":"Rafi", "Phone":01723, "city":"Dhaka"}'
```
### Use the JavaScript function Json parse
```js
var json = '{"name":"rafi", "result":true,"count":2}',
obj = JSON.parse(json);
```
> Use the JavaScript object
```js
<h1 id="demo"></h1> 
<script>
document.getElementById("demo").innerHTML = json.name + ", " + json.city; 
</script>
```
### get data from the server:
```js
var xmlhttp = new XMLHttpRequest();
xmlhttp.onreadystatechange = function() {
    if (this.readyState == 4 && this.status == 200) {
        var myObj = JSON.parse(this.responseText);
        document.getElementById("demo").innerHTML = obj.name;
    }
};
xmlhttp.open("GET", "json_demo.txt", true);
xmlhttp.send();
```
## Json stringify
---
### Json Stringify with JavaScript Object:
```js
var myobj = { "name":"Rafi", "hometown":"Barisal", "currentcity":"Dhaka", "phone":01723****};
```
> JavaScript function JSON.stringify, and string data sent to be a server
```js
var myJSON = JSON.stringify(myobj);
document.getElementById("demo").innerHTML = myJSON;
```
### Json Stringify date:
```js
var myobj = { "name":"Rafi", "date":new Date(), "home":"Barisal" };
```
### Json Stringify function:
```js
var myobj = { "name":"Rafi", "phone":function () {return 01723***;}, "home":"Barisal" };
```
## JSON Schema
---
### Building a product schema:
> JSON data for a product API
```js
{
    "id": 1,
    "name": "Ace Plus",
    "price": 12.50,
    "tags": ["medicine", "drug"]
}
```
> Starting the schema
```js
{
   "$schema": "http://json-schema.org/draft-06/schema#",
   "title": "Product",
   "description": "A product from Medicine",
   "type": "medicine"
}
```
### Defining the properties:
> what is id?
```js
{
   "$schema": "http://json-schema.org/draft-06/schema#",
   "title": "Product",
   "description": "A product from Medicine",
   "type": "object",
   "properties": {
         "id": {
            "description": "The unique indentifier for a product",
            "type": "integer"
         }
     },
    "required": ["id"]
}
```
> Is name required?
```js
{
   "$schema": "http://json-schema.org/draft-06/schema#",
   "title": "Product",
   "description": "A product from Medicine",
   "type": "object",
   "properties": {
         "id": {
             "description": "The unique identifier for a product",
             "type": "integer"
         },
         "name": {
              "description": "Name of the product",
              "type": "string"
         },
         "required": ["id","name"]
}
```
> Can price be 0?
```js
{
    "$schema": "http://json-schema.org/draft-06/schema#",
    "title": "Product",
    "description": "A product from Acme's catalog",
    "type": "object",
    "properties": {
        "id": {
            "description": "The unique identifier for a product",
            "type": "integer"
        },
        "name": {
            "description": "Name of the product",
            "type": "string"
        },
        "price": {
            "type": "number",
            "exclusiveMinimum": 0
        }
    },
    "required": ["id", "name", "price"]
}
```
> Are all tags strings?
```js
{
    "$schema": "http://json-schema.org/draft-06/schema#",
    "title": "Product",
    "description": "A product from Acme's catalog",
    "type": "object",
    "properties": {
        "id": {
            "description": "The unique identifier for a product",
            "type": "integer"
        },
        "name": {
            "description": "Name of the product",
            "type": "string"
        },
        "price": {
            "type": "number",
            "exclusiveMinimum": 0
        },
        "tags": {
            "type": "array",
            "items": {
                "type": "string"
            },
            "minItems": 1,
            "uniqueItems": true
        }
    },
    "required": ["id", "name", "price"]
}
``` 
> Summary of products:
```js
[
    {
        "id": 2,
        "name": "An ice sculpture",
        "price": 12.50,
        "tags": ["cold", "ice"],
        "dimensions": {
            "length": 7.0,
            "width": 12.0,
            "height": 9.5
        },
        "warehouseLocation": {
            "latitude": -78.75,
            "longitude": 20.4
        }
    },
    {
        "id": 3,
        "name": "A blue mouse",
        "price": 25.50,
        "dimensions": {
            "length": 3.1,
            "width": 1.0,
            "height": 1.0
        },
        "warehouseLocation": {
            "latitude": 54.4,
            "longitude": -32.7
        }
    }
]
```
## Json-Examples
---
### JSON with Php
> encode
```js
$myArray = array('Name' => 'Tanbir', 'Age' => 22, 'City' => 'Dhaka', 'Job' => 'nai');
echo json_encode($myArray);
```
> decode
```js
$json = '{"Name": "Tanbir","Age": 22,"City": "Dhaka","Job": "nai"}';
var_dump(json_decode($json));
```
### JSON with Python
> encode
```js
data = [ { 'Name' : 'Rafi', 'Age' : 8, 'City' : 'Dhaka', 'Job' : 'nai'} ]
json = demjson.encode(data)
print json
```
> decode
```js
json = '{"html":5,"css":3,"laravel":5.5}';
text = demjson.decode(json)
print  text
```
### JSON with Java
> encode
```js
class JsonEncodeDemo {

   public static void main(String[] args){
      JSONObject obj = new JSONObject();

      obj.put("name", "rafi");
      obj.put("number", new Integer(01723));
      obj.put("balance", new Double(123450.21));
      obj.put("ip", new Boolean(true));

      System.out.print(obj);
   }
}
```
> decode
```js
String jsonString = "{\"stat\":{\"sdr\": \"aa:bb:cc:dd:ee:ff\",\"rcv\": \"aa:bb:cc:dd:ee:ff\",\"time\": \"UTC in millis\",\"type\": 1,\"subt\": 1,\"argv\": [{1,2},{2,3}]}}";
JSONObject jsonObject = new JSONObject(jsonString);
JSONObject newJSON = jsonObject.getJSONObject("stat");
System.out.println(newJSON);
```

### License 
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

### Admin 
[Tanbir](https://github.com/totanbir)

### Contributors
[contributors](https://github.com/totanbir/json-guide/graphs/contributors)
