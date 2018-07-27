Programació bàsica
==================

Els següents aspectes són molt similars a Java, llenguatge que ja coneixeu:

[Sentències](https://www.w3schools.com/js/js_statements.asp)

[Sintaxi](https://www.w3schools.com/js/js_syntax.asp)

[Comentaris](https://www.w3schools.com/js/js_comments.asp)

Variables
---------
[Teoria completa](https://www.w3schools.com/js/js_variables.asp)

Per declarar variables cal utilitzar `var`, i no s'ha d'indicar el tipus.

```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript Variables</h2>

<p>Strings are written with quotes.</p>
<p>Numbers are written without quotes.</p>

<p id="demo"></p>

<script>
var pi = 3.14;
var person = "John Doe";
var answer = 'Yes I am!';

document.getElementById("demo").innerHTML =
pi + "<br>" + person + "<br>" + answer;
</script>

</body>
</html>



```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_variables_types)


---------------

Continuem amb aspectes similars a Java:

[Operadors](https://www.w3schools.com/js/js_operators.asp)

[Aritmètica](https://www.w3schools.com/js/js_arithmetic.asp)

[Assignació](https://www.w3schools.com/js/js_assignment.asp)

Tipus de dades
---------------
[Teoria completa](https://www.w3schools.com/js/js_datatypes.asp)

### El concepte de Tipus de Dades

Fixa't en el resultat dels següents dos exemples:

```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript</h2>

<p>JavaScript evaluates expressions from left to right. Different sequences can produce different results:</p>

<p id="demo"></p>

<script>
var x = 16 + 4 + "Volvo";
document.getElementById("demo").innerHTML = x;
</script>

</body>
</html>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_datatypes_addstrings_1)

```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript</h2>

<p>JavaScript evaluates expressions from left to right. Different sequences can produce different results:</p>

<p id="demo"></p>

<script>
var x = "Volvo" + 16 + 4;
document.getElementById("demo").innerHTML = x;
</script>

</body>
</html>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_datatypes_addstrings_2)

Perquè el resultat és diferent? La resposta té a veure amb els tipus de dades.

### A JavaScript, els tipus son dinàmics

```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript Data Types</h2>

<p>JavaScript has dynamic types. This means that the same variable can be used to hold different data types:</p>

<p id="demo"></p>

<script>
var x;               // Now x is undefined
x = 5;               // Now x is a Number
x = "John";          // Now x is a String

document.getElementById("demo").innerHTML = x;
</script>

</body>
</html>
```
[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_datatypes_dynamic)

### Strings
```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript Strings</h2>

<p>You can use quotes inside a string, as long as they don't match the quotes surrounding the string:</p>

<p id="demo"></p>

<script>
var answer1 = "It's alright";
var answer2 = "He is called 'Johnny'";
var answer3 = 'He is called "Johnny"';

document.getElementById("demo").innerHTML =
answer1 + "<br>" +
answer2 + "<br>" +
answer3;
</script>

</body>
</html>
```

### Números

JavaScript només té un tipus de número.

```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript Numbers</h2>

<p>Numbers can be written with, or without decimals:</p>

<p id="demo"></p>

<script>
var x1 = 34.00;
var x2 = 34;
var x3 = 3.14;

document.getElementById("demo").innerHTML =
x1 + "<br>" + x2 + "<br>" + x3;
</script>

</body>
</html>
```
[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_datatypes_numbers)

### Booleans

```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript Booleans</h2>

<p>Booleans can have two values: true or false:</p>

<p id="demo"></p>

<script>
var x = 5;
var y = 5;
var z = 6;
document.getElementById("demo").innerHTML =
(x == y) + "<br>" + (x == z);
</script>

</body>
</html>
```
[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_datatypes_bolean)

### Arrays

```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript Arrays</h2>

<p>Array indexes are zero-based, which means the first item is [0].</p>

<p id="demo"></p>

<script>
var cars = ["Saab","Volvo","BMW"];

document.getElementById("demo").innerHTML = cars[0];
</script>

</body>
</html>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_datatypes_array)

### Objectes
```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript Objects</h2>

<p id="demo"></p>

<script>
var person = {
    firstName : "John",
    lastName  : "Doe",
    age       : 50,
    eyeColor  : "blue"
};

document.getElementById("demo").innerHTML =
person.firstName + " is " + person.age + " years old.";
</script>

</body>
</html>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_datatypes_object)

### Funcions

Es veurà més endavant.
