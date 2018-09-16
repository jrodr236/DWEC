Elements DOM
=========

[Teoria completa](https://www.w3schools.com/js/js_htmldom_elements.asp)

Abans de manipular elements HTML, primer els hem de trobar.

Trobar elements HTML per l'id
---------------

```html
<!DOCTYPE html>
<html>
<body>

<p id="intro">Hello World!</p>

<p>This example demonstrates the <b>getElementById</b> method!</p>

<p id="demo"></p>

<script>
var myElement = document.getElementById("intro");
document.getElementById("demo").innerHTML = 
"The text from the intro paragraph is " + myElement.innerHTML;
</script>

</body>
</html>
```
[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_dom_getelementbyid)

Trobar elements HTML pel nom d'etiqueta
--------------------

```html
<!DOCTYPE html>
<html>
<body>

<p>Hello World!</p>

<p>The DOM is very useful.</p>
<p>This example demonstrates the <b>getElementsByTagName</b> method</p>

<p id="demo"></p>

<script>
var x = document.getElementsByTagName("p");
document.getElementById("demo").innerHTML = 
'The first paragraph (index 0) is: ' + x[0].innerHTML;
</script>

</body>
</html>
```
[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_dom_getelementsbytagname2)


```html
<!DOCTYPE html>
<html>
<body>

<p>Hello World!</p>

<div id="main">
<p>The DOM is very useful.</p>
<p>This example demonstrates the <b>getElementsByTagName</b> method</p>
</div>

<p id="demo"></p>

<script>
var x = document.getElementById("main");
var y = x.getElementsByTagName("p");
document.getElementById("demo").innerHTML = 
'The first paragraph (index 0) inside "main" is: ' + y[0].innerHTML;
</script>

</body>
</html>
```
[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_dom_getelementsbytagname)


Trobar elements HTML pel nom de classe
--------------
```html
<!DOCTYPE html>
<html>
<body>

<p>Hello World!</p>

<p class="intro">The DOM is very useful.</p>
<p class="intro">This example demonstrates the <b>getElementsByClassName</b> method.</p>

<p id="demo"></p>

<script>
var x = document.getElementsByClassName("intro");
document.getElementById("demo").innerHTML = 
'The first paragraph (index 0) with class="intro": ' + x[0].innerHTML;
</script>

</body>
</html>
```
[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_dom_getelementsbyclassname)




Trobar elements HTML pel selector CSS
-----------------------

```html
<!DOCTYPE html>
<html>
<body>

<p>Hello World!</p>

<p class="intro">The DOM is very useful.</p>
<p class="intro">This example demonstrates the <b>querySelectorAll</b> method.</p>

<p id="demo"></p>

<script>
var x = document.querySelectorAll("p.intro");
document.getElementById("demo").innerHTML = 
'The first paragraph (index 0) with class="intro": ' + x[0].innerHTML;
</script>

</body>
</html>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_dom_queryselectorall)


Trobar elements HTML per la col·lecció d'objectes HTML
---------------------------
```html
<!DOCTYPE html>
<html>
<body>

<form id="frm1" action="/action_page.php">
  First name: <input type="text" name="fname" value="Donald"><br>
  Last name: <input type="text" name="lname" value="Duck"><br><br>
  <input type="submit" value="Submit">
</form> 

<p>Click "Try it" to display the value of each element in the form.</p>

<button onclick="myFunction()">Try it</button>

<p id="demo"></p>

<script>
function myFunction() {
    var x = document.forms["frm1"];
    var text = "";
    var i;
    for (i = 0; i < x.length ;i++) {
        text += x.elements[i].value + "<br>";
    }
    document.getElementById("demo").innerHTML = text;
}
</script>

</body>
</html>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_dom_form_elements)


