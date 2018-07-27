Objectes
=======

[*Teoria completa*](https://www.w3schools.com/js/js_objects.asp)

Recordem: objecte = propietats + mètodes

```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript Objects</h2>

<p>An object method is a function definition, stored as a property value.</p>

<p id="demo"></p>

<script>
// Create an object:
var person = {
    firstName: "John",
    lastName : "Doe",
    id       : 5566,
    fullName : function() {
       return this.firstName + " " + this.lastName;
    }
};
// Display data from the object:
document.getElementById("demo").innerHTML = person.fullName();
</script>
</body>
</html>
```

[demo](https://www.w3schools.com/js/tryit.asp?filename=tryjs_objects_method)

Diferència amb Java: en l'exemple s'ha definit (i creat) un objecte amb un literal. Tot i que es poden declarar classes, no és necessari per crear un objecte.
