Creació i navegació pels nodes DOM
=============

Navegació
------

[Teoria completa](https://www.w3schools.com/js/js_htmldom_eventlistener.asp)

![DOM tree](https://www.w3schools.com/js/pic_htmltree.gif)

Podem navegar per l'arbre del DOM utilitzant les relacions entre els nodes.

![Relacions entre els nodes](https://www.w3schools.com/js/pic_navigate.gif)

```html
<html>

  <head>
      <title>DOM Tutorial</title>
  </head>

  <body>
      <h1>DOM Lesson one</h1>
      <p>Hello world!</p>
  </body>

  <script>
    
  </script>

</html>
```

Obrir `Console (F12)`:
```JavaScript
document;

document.firstElementChild;

document.firstElementChild.firstElementChild;

document.firstElementChild.firstElementChild.nextElementSibling;

document.firstElementChild.firstElementChild.nextElementSibling.firstElementChild;

document.firstElementChild.firstElementChild.nextElementSibling.firstElementChild.nextElementSibling;
```

Nodes
-----

[Teoria completa](https://www.w3schools.com/js/js_htmldom_nodes.asp)

### Creant nous elements HTML (nodes):

```html
<!DOCTYPE html>
<html>
<body>

<div id="div1">
<p id="p1">This is a paragraph.</p>
<p id="p2">This is another paragraph.</p>
</div>

<script>
var para = document.createElement("p");
var node = document.createTextNode("This is new.");
para.appendChild(node);
var element = document.getElementById("div1");
element.appendChild(para);
</script>

</body>
</html>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_dom_elementcreate)


#### Explicació

* Aquest codi crea un nou element `<p>`:

   ```JavaScript
   var para = document.createElement("p");
   ```
* Per afegir text a l'element <p>, cal crear un node de text primer. Aquest codi crea un node de text:

   ```JavaScript
   var node = document.createTextNode("This is a new paragraph.");
   ```
* Llavors s'ha d'afegir el node de text a l'element `<p>`:
   ```JavaScript
   para.appendChild(node);
   ```
* Finalment, cal afegir el nou element a l'element existent.

  Aquest codi busca l'element existent:

   ```JavaScript
   var element = document.getElementById("div1");
   ```
* Aquest codi afegeix el nou element a l'element existent:
   ```JavaScript
   element.appendChild(para);
   ```

### Altres operacions

També és possible:
- Inserir elements _abans_ que un altre element existent
- Eliminar elements existents.
- Reemplaçar elements
Es poden trobar les explicacions d'aquestes tasques a l'[apartat de w3schools corresponent](https://www.w3schools.com/js/js_htmldom_nodes.asp).


Col·leccions
---------

[Teoria completa](https://www.w3schools.com/js/js_htmldom_collections.asp)

### L'objecte `HTMLCollection`

El mètode `getElementsByTagName()` retorna un objecte `HTMLCollection`.

Un objecte `HTMLCollection` és com un _array list_ (col·lecció) d'elements HTML.

```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript HTML DOM</h2>

<p>Hello World!</p>

<p>Hello Norway!</p>

<p id="demo"></p>

<script>
var myCollection = document.getElementsByTagName("p");
document.getElementById("demo").innerHTML =
"The innerHTML of the second paragraph is: " +
myCollection[1].innerHTML;
</script>

</body>
</html>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_dom_htmlcollection)

### La longitud (`lenght`) de l'`HTMLCollection`

```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript HTML DOM</h2>

<p>Hello World!</p>

<p>Hello Norway!</p>

<p>Click the button to change the color of all p elements.</p>

<button onclick="myFunction()">Try it</button>

<script>
function myFunction() {
    var myCollection = document.getElementsByTagName("p");
    var i;
    for (i = 0; i < myCollection.length; i++) {
        myCollection[i].style.color = "red";
    }
}
</script>

</body>
</html>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_dom_htmlcollection_loop)


> **`HTMLCollection` no és un array!**
>
> `HTMLCollection` pot semblar un array, però no ho és.
>
> Pots recòrrer a la llista i referir-te als elements amb un número (igual que un array).
>
>
> Però no pot utilitzar els mètodes dels arrays com `valueOf()`, `pop()`, `push()`, o `join()` en un `HTMLCollection`.


Llistes de nodes
-------------

[Teoria completa](https://www.w3schools.com/js/js_htmldom_nodelist.asp)

Els objectes `NodeList` son molt semblants als objectes `HTMLCollection`. 

Alguns navegadors antics retornen un objecte `NodeList` enlloc d'un `HTMLCollection` en determinats mètodes.

També hi han mètodes que retornen `NodeList` en tots els navegadors.

Veure l'[apartat corresponent de w3schools](https://www.w3schools.com/js/js_htmldom_nodelist.asp) si cal més informació.