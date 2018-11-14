Creant una llista dinàmica i animada
===================

{% raw %}

```html
<!DOCTYPE html>
<html>

<head>
  <title></title>
  <script src="https://unpkg.com/vue/dist/vue.js"></script>
</head>

<body>
  <div id="app">
    <ul>
      <li v-for="n in countdown">{{n}}</li>
      <li>launch missile!</li>
    </ul>
  </div>

  <script>
    var vm = new Vue({
      el: '#app',
      data: {
        countdown: []
      }
    })
    var counter = 10
    setInterval(function () {
      if (counter > 0) {
        vm.countdown.push(counter--)
      }
    }, 1000)
  </script>
</body>

</html>
```

Si fessim `vm.countdown[counter] = counter--`, l'array s'actualitzaria però el sistema _reactiu_ de Vue no funcionaria, per com està implementat JavaScript.

Passa el mateix si volem modificar un element, o la longitud d'un array. 

```JavaScript
vm.reactiveArray[index] = 'updated value'
vm.reactiveArray.length = 0
```
Així no s'actualitza la vista. Es pot superar aquesta limitació amb el mètode `splice`:

```JavaScript
vm.reactiveArray.splice(index, 1, 'updated value')
vm.reactiveArray.splice(0)
```

---

```html
<!DOCTYPE html>
<html>

<head>
  <title></title>
  <script src="https://unpkg.com/vue/dist/vue.js"></script>
</head>

<body>
  <div id="app">
    <ul>
      <li v-for="n in countdown">{{n}}</li>
      <li>{{ countdown.length === 10 ? 'launch missile!' : '...' }}</li>
    </ul>
  </div>

  <script>
    var vm = new Vue({
      el: '#app',
      data: {
        countdown: []
      }
    })
    var counter = 10
    setInterval(function () {
      if (counter > 0) {
        vm.countdown.push(counter--)
      }
    }, 1000)
  </script>
</body>

</html>
```

Veurem una solució millor més endavant amb `v-show`.

{% endraw %}