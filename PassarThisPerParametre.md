Passar _this_ per paràmetre
============================

La paraula reservada [_this_](https://www.w3schools.com/js/js_this.asp) fa referència a l'objecte al qual es pertany. Depèn del context pot significar una cosa o una altra.

És molt interessant poder fer arribar _this_ al _handler_ d'un event. Com?

Recuperem el següent exemple:

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

Repliquem els `<div>`. Funciona gràcies a que es passa el context (`this`) per paràmetre.

```html
<!DOCTYPE html>
<html>
<body>

<div onmousedown="mDown(this)" onmouseup="mUp(this)"
style="background-color:#D94A38;width:90px;height:20px;padding:40px;">
Click Me</div>

<br>

<div onmousedown="mDown(this)" onmouseup="mUp(this)"
style="background-color:#D94A38;width:90px;height:20px;padding:40px;">
Click Me</div>

<br>

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

Com podem millorar aquest codi utilitzant `addEventListener()`?

Això no funciona, perquè no es passa la funció per paràmetre, sinò que s'executa i es passa per paràmetre el seu valor de retorn:

```javascript
var divs = document.getElementsByTagName("div");
var i;
for (i = 0; i < divs.length; i++) {
    divs[i].addEventListener('mouseup', mUp(this));
	divs[i].addEventListener('mousedown', mDown(this));
}
```

Això tampoc funciona, perquè no podem passar el paràmetre _this_ per paràmetre:

```javascript
var divs = document.getElementsByTagName("div");
var i;
for (i = 0; i < divs.length; i++) {
    divs[i].addEventListener('mouseup', mUp);
	divs[i].addEventListener('mousedown', mDown);
}
```

La solució és la següent:

```html
<!DOCTYPE html>
<html>
<body>

<div style="background-color:#D94A38;width:90px;height:20px;padding:40px;">
Click Me</div>

<br>

<div style="background-color:#D94A38;width:90px;height:20px;padding:40px;">
Click Me</div>

<br>

<div style="background-color:#D94A38;width:90px;height:20px;padding:40px;">
Click Me</div>

<script>

var divs = document.getElementsByTagName("div");
var i;
for (i = 0; i < divs.length; i++) {
    divs[i].addEventListener('mouseup', function() {
		mUp(this);
	});
	divs[i].addEventListener('mousedown', function() {
		mDown(this);
	});
}


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