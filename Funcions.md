Funcions
=========

[*Teoria completa*](https://www.w3schools.com/js/js_functions.asp)


```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript Functions</h2>

<p>This example calls a function which performs a calculation, and returns the result:</p>

<p id="demo"></p>

<script>
function myFunction(p1, p2) {
    return p1 * p2;
}
document.getElementById("demo").innerHTML = myFunction(4, 3);
</script>

</body>
</html>
```
[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_functions)

Sintaxi
----------

```JavaScript
function name(parameter1, parameter2, parameter3) {
    code to be executed
}
```

Diferències amb Java:
* Les funcions es defineixen amb la paraula ```function```.
* Els paràmetres no tenen tipus definit.

L'operador `()` invoca a la funció
-------------------

```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript Functions</h2>

<p>Accessing a function without () will return the function definition instead of the function result:</p>
<p id="demo"></p>

<script>
function toCelsius(f) {
    return (5/9) * (f-32);
}
document.getElementById("demo").innerHTML = toCelsius;
</script>

</body>
</html>
```
[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_farenheit_to_celsius_2)
