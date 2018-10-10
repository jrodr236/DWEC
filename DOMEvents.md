Events DOM
==========

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

(...)
