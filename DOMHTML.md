Canviant l'HTML
======

[Teoria Completa](https://www.w3schools.com/js/js_htmldom_html.asp)

```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript can Change HTML</h2>

<p id="p1">Hello World!</p>

<script>
document.getElementById("p1").innerHTML = "New text!";
</script>

<p>The paragraph above was changed by a script.</p>

</body>
</html>

```
[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_change_innerhtml)

```html
<!DOCTYPE html>
<html>
<body>

<h1 id="id01">Old Heading</h1>

<script>
var element = document.getElementById("id01");
element.innerHTML = "New Heading";
</script>

<p>JavaScript changed "Old Heading" to "New Heading".</p>

</body>
</html> 
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_dom_innerhtml)

```html
<!DOCTYPE html>
<html>
<body>

<img id="image" src="smiley.gif" width="160" height="120">

<script>
document.getElementById("image").src = "landscape.jpg";
</script>

<p>The original image was smiley.gif, but the script changed it to landscape.jpg</p>

</body>
</html>
```
[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_dom_image)

