Events DOM
==========

Reaccionant a events
---------------------------

Un codi JavaScript es pot executar quan succeeix un event (o esdeveniment). Per exemple, quan l'usuari fa _clic_ a un element HTML.

Per executar codi quan un usuari fa _clic_ a un element, afegir el següent codi JavaScript a l'atribut HTML _event_:

```html
onclick=JavaScript
```

Exemples d'events HTML:
- Quan un usuari fa _clic_ amb el ratolí
- Quan una pàgina web s'ha carregat
- Quan una imatge s'ha carregat
- Quan el ratolí es mou per sobre d'un element
- Quan un camp `<input>` es canvia
- Quan es fa _submit_ a un formulari
- Quan l'usuari pressiona una tecla

Com assignar codi JavaScript als events?
------------------------

### Malament

Al següent exemple, el codi està escrit directament a l'etiqueta HTML:

```html
<!DOCTYPE html>
<html>
<body>

<h1 onclick="this.innerHTML = 'Ooops!'">Click on this text!</h1>

</body>
</html>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_event_onclick2)

### Una mica millor

Una forma millor, per separar una mica el contingut (html) de la funcionalitat (JavaScript) és fer servir una funció:

```html
<!DOCTYPE html>
<html>
<body>

<h1 onclick="changeText(this)">Click on this text!</h1>

<script>
function changeText(id) { 
    id.innerHTML = "Ooops!";
}
</script>

</body>
</html>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_event_onclick3)

### Força millor

Una forma encara millor d'assignar events a codi HTML és fer-ho des del propi codi JavaScript. Així aconseguim separar totalment el contingut (html), el format (css), i el comportament (JavaScript):

```html
<!DOCTYPE html>
<html>
<body>

<p>Click "Try it" to execute the displayDate() function.</p>

<button id="myBtn">Try it</button>

<p id="demo"></p>

<script>
document.getElementById("myBtn").onclick = displayDate;

function displayDate() {
    document.getElementById("demo").innerHTML = Date();
}
</script>

</body>
</html> 
```

[Demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_events2)

### La millor

La millor forma d'assignar events és utilitzar `addEventListener()`, i la veurem el proper apartat.

Events `onload` i `onunload`
------------

Els esdeveniments `onload` i `onunload` es llançen quan l'usuari entra o surt de la pàgina.

```html
<!DOCTYPE html>
<html>
<body onload="checkCookies()">

<p id="demo"></p>

<script>
function checkCookies() {
    var text = "";
    if (navigator.cookieEnabled == true) {
        text = "Cookies are enabled.";
    } else {
        text = "Cookies are not enabled.";
    }
    document.getElementById("demo").innerHTML = text;
}
</script>

</body>
</html> 
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_events_onload)

Event `onchange`
------

L'event `onchange` s'utilitza habitualment combinats amb la validació dels camps `<input>`

```html
<!DOCTYPE html>
<html>
<head>
<script>
function myFunction() {
    var x = document.getElementById("fname");
    x.value = x.value.toUpperCase();
}
</script>
</head>
<body>

Enter your name: <input type="text" id="fname" onchange="myFunction()">
<p>When you leave the input field, a function is triggered which transforms the input text to upper case.</p>

</body>
</html>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_onchange)

Events `onmouseover` i `onmouseout`
------------------

```html
<!DOCTYPE html>
<html>
<body>

<div onmouseover="mOver(this)" onmouseout="mOut(this)" 
style="background-color:#D94A38;width:120px;height:20px;padding:40px;">
Mouse Over Me</div>

<script>
function mOver(obj) {
    obj.innerHTML = "Thank You"
}

function mOut(obj) {
    obj.innerHTML = "Mouse Over Me"
}
</script>

</body>
</html> 
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_events_mouseover)

Events onmousedown, onmouseup i onclick
-------------------------------

```html
<!DOCTYPE html>
<html>
<body>

<div onmousedown="mDown(this)" onmouseup="mUp(this)"
style="background-color:#D94A38;width:90px;height:20px;padding:40px;">
Click Me</div>

<script>
function mDown(obj) {
    obj.style.backgroundColor = "#1ec5e5";
    obj.innerHTML = "Release Me";
}

function mUp(obj) {
    obj.style.backgroundColor="#D94A38";
    obj.innerHTML="Thank You";
}
</script>

</body>
</html> 
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_events_mousedown)

