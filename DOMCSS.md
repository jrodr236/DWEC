Canviant el CSS
=======

[Teoria Completa](https://www.w3schools.com/js/js_htmldom_css.asp)

```html
<!DOCTYPE html>
<html>
<body>

<p id="p1">Hello World!</p>
<p id="p2">Hello World!</p>

<script>
document.getElementById("p2").style.color = "blue";
document.getElementById("p2").style.fontFamily = "Arial";
document.getElementById("p2").style.fontSize = "larger";
</script>

<p>The paragraph above was changed by a script.</p>

</body>
</html>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_change_style)

```html
<!DOCTYPE html>
<html>
<body>

<h1 id="id1">My Heading 1</h1>

<button type="button" 
onclick="document.getElementById('id1').style.color = 'red'">
Click Me!</button>

</body>
</html>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_dom_color2)

