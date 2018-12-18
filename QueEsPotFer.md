Què es pot fer amb Javascript?
----------------------

[*Teoria completa*](https://www.w3schools.com/js/js_intro.asp)


### Canviar contingut

```html
<!DOCTYPE html>
<html>
<body>

<h2>What Can JavaScript Do?</h2>

<p id="demo">JavaScript can change HTML content.</p>

<button type="button" onclick='document.getElementById("demo").innerHTML = "Hello JavaScript!"'>Click Me!</button>

</body>
</html>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_intro_inner_html)

### Canviar valors d'atributs



```html
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

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_intro_lightbulb
)
### Canviar estils



```html
<!DOCTYPE html>
<html>
<body>

<h2>What Can JavaScript Do?</h2>

<p id="demo">JavaScript can change the style of an HTML element.</p>

<button type="button" onclick="document.getElementById('demo').style.fontSize='35px'">Click Me!</button>


</body>
</html>
```
[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_intro_style)


### Ocultar elements



```html
<!DOCTYPE html>
<html>
<body>

<h2>What Can JavaScript Do?</h2>

<p id="demo">JavaScript can hide HTML elements.</p>

<button type="button" onclick="document.getElementById('demo').style.display='none'">Click Me!</button>


</body>
</html>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_intro_hide)



### Mostrar elements



```html
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

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_intro_show)

-------

Fixa't en dos aspectes importants:
* **Events**: "coses" que passen en els elements HTML. JavaScript pot "reaccionar" a aquests events.
* **Accés al DOM**: JavaScript pot accedir i canviar tots els elements del document HTML.
