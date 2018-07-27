A on?
====

[*Teoria completa*](https://www.w3schools.com/js/js_whereto.asp)

L'etiqueta `<script>`
-------------------

```html
<script>
document.getElementById("demo").innerHTML = "My First JavaScript";
</script>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_whereto)


Javascript al `<head>`
---------------------
```html
<!DOCTYPE html>
<html>
<head>
<script>
function myFunction() {
    document.getElementById("demo").innerHTML = "Paragraph changed.";
}
</script>
</head>

<body>

<h2>JavaScript in Head</h2>

<p id="demo">A Paragraph.</p>

<button type="button" onclick="myFunction()">Try it</button>

</body>
</html>
```
[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_whereto_head)


JavaScript al `<body>`
-------------------
S'ha de posar al final per no ralentitzar la càrrega de la
pàgina.

```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript in Body</h2>

<p id="demo">A Paragraph.</p>

<button type="button" onclick="myFunction()">Try it</button>

<script>
function myFunction() {
    document.getElementById("demo").innerHTML = "Paragraph changed.";
}
</script>

</body>
</html>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_whereto_body)



JavaScript extern
--------------


```html
<!DOCTYPE html>
<html>
<body>

<h2>External JavaScript</h2>

<p id="demo">A Paragraph.</p>

<button type="button" onclick="myFunction()">Try it</button>

<p>(myFunction is stored in an external file called "myScript.js")</p>

<script src="myScript.js"></script>

</body>
</html>
```

myScript.js
```JavaScript
function myFunction() {
    document.getElementById("demo").innerHTML="Paragraph changed.";
}
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_whereto_external)

### Avantatges

* Separa HTML i codi
* Fa que l'HTML I el JavaScript siguin més fàcil de llegir i mantenir
* Els fitxers JavaScript en caché augmenten la velocitat de càrrega de la pàgina
