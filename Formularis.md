Formularis de JavaScript
=========

[*Teoria completa*](https://www.w3schools.com/js/js_validation.asp)

Validació de dades
------------------

La validació de dades és el procés d'assegurar-se que l'entrada de l'usuari és neta, correcta i útil.

Les tasques típiques de validació son:

- L'usuari ha omplert totes des dades requerides?
- L'usuari ha entrat dades vàlides?
- L'usuari ha entrat text en un camp numèric?

La validació pot definir-se utilitzant diferents mètodes:
- **Validació al costat del servidor**: es realitza al servidor web, després que l'entrada hagi arribat al servidor.
- **Validació al costat del client**: es realitza pel navegador web, abans que l'enterada s'envïi al servidor web.



Validació de formularis amb JavaScript
---------

```html
<!DOCTYPE html>
<html>
<head>
<script>
function validateForm() {
    var x = document.forms["myForm"]["fname"].value;
    if (x == "") {
        alert("Name must be filled out");
        return false;
    }
}
</script>
</head>
<body>

<form name="myForm" action="/action_page.php"
onsubmit="return validateForm()" method="post">
Name: <input type="text" name="fname">
<input type="submit" value="Submit">
</form>

</body>
</html>
```
[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_validation_js)


```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript Can Validate Input</h2>

<p>Please input a number between 1 and 10:</p>

<input id="numb">

<button type="button" onclick="myFunction()">Submit</button>

<p id="demo"></p>

<script>
function myFunction() {
    var x, text;

    // Get the value of the input field with id="numb"
    x = document.getElementById("numb").value;

    // If x is Not a Number or less than one or greater than 10
    if (isNaN(x) || x < 1 || x > 10) {
        text = "Input not valid";
    } else {
        text = "Input OK";
    }
    document.getElementById("demo").innerHTML = text;
}
</script>

</body>
</html> 
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_validation_number)


Validació de formularis amb HTML/CSS
---------------------------

Per exemple, amb l'atribut ```required```

```html
<!DOCTYPE html>
<html>
<body>

<form action="/action_page.php" method="post">
  <input type="text" name="fname" required>
  <input type="submit" value="Submit">
</form>

<p>If you click submit, without filling out the text field,
your browser will display an error message.</p>

</body>
</html>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_validation_html)

Veure el concepte _HTML Constant Validation_ a [w3schools > JavaScript Forms > HTML Constraint Validation](https://www.w3schools.com/js/js_validation.asp)

Veure la forma d'interactuar amb JavaScript amb els elements de validació d'HTML a [w3schools > JavaScript Validation API](https://www.w3schools.com/js/js_validation_api.asp)