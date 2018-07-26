Introducció a Javascript
======================

Què és Javascript?
---------------

Javascript és el que es coneix com un llenguatge de script, es tracta de codi de programació inserit en un document.

Va ser desenvolupat per la empresa Netscape amb la idea de potenciar portals web dinàmiques amb navegador Netscape Navigator.

Javascript és interpretat directament pel navegador i per tant necessita accedir als elements HTML de la pàgina.

La definició del [MDN](https://developer.mozilla.org/ca/docs/Web/JavaScript) és:
> JavaScript® (tot sovint abreujat com a JS) és un llenguatge orientat a objectes, lleuger i interpretat, amb [funcions de primera classe](https://en.wikipedia.org/wiki/First-class_functions), més conegut per ser el llenguatge d'scripting per a pàgines Web, però també utilitzat en molts àmbits fora d'un navegador web com ara [node.js](http://nodejs.org/) o [Apache CouchDB](http://couchdb.apache.org/).

Història
---------
A principis dels anys 90 començaven a desenvolupar-se les primeres aplicacions web, i per tant les pàgines començaven a incloure formularis.

Amb unes aplicacions web cada cop més complexes i una velocitat de navegació lenta, va sorgir la necessitat d'un **llenguatge de programació que s'executés en el navegador** de l'usuari.

En cas que l'usuari no omplis correctament un formulari, no se’l feia esperar molt temps fins que el servidor tornés a mostrar el formulari indicant els errors existents.

**Brendan Eich**, un programador que treballava en Netscape, va pensar que podria solventar el problema adaptant altres tecnologies existents (com ScriptEase) al navegador Netscape Navigator 2.0.

Inicialmente Eich va anomenar al seu llenguatge **LiveScript**.

Al mateix temps, **Microsoft** va llançar **JScript** amb **Internet Explorer 3**. JScript era una copia de JavaScript al que li van canviar el nom per evitar problemes legals.

Netscape va decidir estandaritzar el llenguatge JavaScript. El 1997 es va enviar la especificació JavaScript 1.1 al organisme ECMA (European Computer Manufacturers Association).

El primer estàndard que va crear ECMA es va denominar **ECMA-262**, en el que es va definir per primer cop el llenguatge **ECMAScript**.

JavaScript no es més que la implementació realitzada per Netscape del estàndar [ECMAScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Language_Resources).

ECMA ha publicat diferents edicions relacionades amb ECMAScript.

A data d’avui la gran majoria de navegadors suporten l’estàndard **ECMAScript 5.1**.

La última versió és **ECMAScript 9** publicada al Juny de 2018.



Què es pot fer amb Javascript?
----------------------

[*Teoria completa*](https://www.w3schools.com/js/js_intro.asp)

Anem a veure alguns exemples:

### Canviar contingut

```JavaScript
<!DOCTYPE html>
<html>
<body>

<h2>What Can JavaScript Do?</h2>

<p id="demo">JavaScript can change HTML content.</p>

<button type="button" onclick='document.getElementById("demo").innerHTML = "Hello JavaScript!"'>Click Me!</button>

</body>
</html>
```

### Canviar valors d'atributs

```JavaScript
<!DOCTYPE html>
<html>
<body>

<h2>What Can JavaScript Do?</h2>

<p>JavaScript can change HTML attribute values.</p>

<p>In this case JavaScript changes the value of the src (source) attribute of an image.</p>

<button onclick="document.getElementById('myImage').src='https://www.w3schools.com/js/pic_bulbon.gif'">Turn on the light</button>

<img id="myImage" src="https://www.w3schools.com/js/pic_bulboff.gif" style="width:100px">

<button onclick="document.getElementById('myImage').src='https://www.w3schools.com/js/pic_bulboff.gif'">Turn off the light</button>

</body>
</html>
```

### Canviar estils

```Javascript
<!DOCTYPE html>
<html>
<body>

<h2>What Can JavaScript Do?</h2>

<p id="demo">JavaScript can change the style of an HTML element.</p>

<button type="button" onclick="document.getElementById('demo').style.fontSize='35px'">Click Me!</button>


</body>
</html>
```

### Ocultar elements

```Javascript
<!DOCTYPE html>
<html>
<body>

<h2>What Can JavaScript Do?</h2>

<p id="demo">JavaScript can hide HTML elements.</p>

<button type="button" onclick="document.getElementById('demo').style.display='none'">Click Me!</button>


</body>
</html>
```

### Mostrar elements

```JavaScript
<!DOCTYPE html>
<html>
<body>

<h2>What Can JavaScript Do?</h2>

<p>JavaScript can show hidden HTML elements.</p>

<p id="demo" style="display:none">Hello JavaScript!</p>

<button type="button" onclick="document.getElementById('demo').style.display='block'">Click Me!</button>

</body>
</html>
```
