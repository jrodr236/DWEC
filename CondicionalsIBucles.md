Condicionals i bucles
=================

Son molt semblants als de Java.

Comparadors i operadors lògics
----------------------

[Veure teoria completa](https://www.w3schools.com/js/js_comparisons.asp)

Reflexiona: perquè el següent codi retorna `false`?

```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript Comparison</h2>

<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = "2" < "12";
</script>

</body>
</html>
```
[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_comparison_26)


Switch
------
[Veure teoria completa](https://www.w3schools.com/js/js_switch.asp)

```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript switch</h2>

<p id="demo"></p>

<script>
var text;
switch (new Date().getDay()) {
    case 6:
        text = "Today is Saturday";
        break;
    case 0:
        text = "Today is Sunday";
        break;
    default:
        text = "Looking forward to the Weekend";
}
document.getElementById("demo").innerHTML = text;
</script>

</body>
</html>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_switch2)


Bucle for
------
[Veure teoria completa](https://www.w3schools.com/js/js_loop_for.asp)

```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript Loops</h2>

<p id="demo"></p>

<script>
var text = "";
var i;
for (i = 0; i < 5; i++) {
    text += "The number is " + i + "<br>";
}
document.getElementById("demo").innerHTML = text;
</script>

</body>
</html>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_loop_for_ex)


```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript Loops</h2>

<p>The for/in statement loops through the properties of an object.</p>

<p id="demo"></p>

<script>
var txt = "";
var person = {fname:"John", lname:"Doe", age:25};
var x;
for (x in person) {
    txt += person[x] + " ";
}
document.getElementById("demo").innerHTML = txt;
</script>

</body>
</html>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_object_for_in)


Bucle while
-----
[Veure teoria completa](https://www.w3schools.com/js/js_loop_while.asp)

```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript while</h2>

<p id="demo"></p>

<script>
var text = "";
var i = 0;
while (i < 10) {
    text += "<br>The number is " + i;
    i++;
}
document.getElementById("demo").innerHTML = text;
</script>

</body>
</html>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_while)

```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript do ... while</h2>

<p id="demo"></p>

<script>
var text = ""
var i = 0;

do {
    text += "<br>The number is " + i;
    i++;
}
while (i < 10);  

document.getElementById("demo").innerHTML = text;
</script>

</body>
</html>
```
[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_dowhile)
