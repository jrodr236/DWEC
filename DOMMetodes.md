Mètodes DOM
=========

[Teoria completa](https://www.w3schools.com/js/js_htmldom_methods.asp)

Al DOM, tots els elements HTML son definits com objectes.

Els mètodes DOM son accions que pots realitzar sobre els elements HTML.

Les propietats DOM son valors dels elements HTML que pots canviar.

```html
<!DOCTYPE html>
<html>
<body>

<h2>My First Page</h2>

<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = "Hello World!";
</script>

</body>
</html>
```

A l'exemple anterior, `getElementById` és un **mètode**, i `innerHTML` és una **propietat**.

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_dom_method)


La forma més habitual d'accedir a un element HTML és mitjançant el mètode `getElementById`.

La forma més senzilla d'obtenir el contingut d'un element és utilitzant la propietat `innerHTML`.

