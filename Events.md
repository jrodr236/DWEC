Events
=====

[*Teoria completa*](https://www.w3schools.com/js/js_events.asp)

Els events d'HTML son **"coses"** que passen als elements HTML.

JavaScript pot **"reaccionar"** a aquests events.

Exemples d'events:
* Una pàgina HTML s'acaba de carregar
* Un camp d'entrada canvia
* Es clica un botó

```html
<!DOCTYPE html>
<html>
<body>

<p>Click the button to display the date.</p>

<button onclick="displayDate()">The time is?</button>

<script>
function displayDate() {
    document.getElementById("demo").innerHTML = Date();
}
</script>

<p id="demo"></p>

</body>
</html>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_events1)

Alguns events habituals:
* onchange: s'ha canviat un element HTML
* onclick: l'usuari fa clic a un element HTML
* onmouseover: l'usuari mou el ratolí a sobre d'un element HTML
* onmouseout: l'usuari treu el ratolí d'un element HTML
* onkeydown: L'usuari pressiona una tecla
* onload: el navegador acaba de carregar una pàgina
