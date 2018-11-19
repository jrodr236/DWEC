Reaccionant a events com clics o pulsacions de tecles
===============================================

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
    <button v-on:click="toast">Toast bread</button>
  </div>

  <script>
    new Vue({
	  el:'#app',
	  methods: {
	    toast() {
		  alert('Tosted!')
		}
      }
	})
  </script>
</body>
</html>
```

Two-way data binding (Enllaç de dades bidireccionals)
--------------

```html
<!DOCTYPE html>
<html>
<head>
  <title></title>
  <script src="https://unpkg.com/vue/dist/vue.js"></script>
</head>
<body>
  <div id="app">
    <button v-on:click="toast">Toast bread</button>
    <input v-model="toastedBreads" />
    Quantity to put in the oven: {{toastedBreads}}
  </div>

  <script>
    new Vue({
      el: '#app',
      methods: {
        toast () {
          this.toastedBreads++
        }
      },
      data: {
        toastedBreads: 0
      }
    })
  </script>
</body>
</html>
```

Afegim més interactivitat
-------------------

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
      <li v-for="world in worlds">{{world}}</li>
    </ul>
  </div>

  <script>
    new Vue({
      el: '#app',
      data: {
        worlds: ['Terran', 'L24-D', 'Ares', 'New Kroy', 'Sebek', 'Vestra']
      }
    })
  </script>
</body>
</html>
```

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
      <li v-for="(world, i) in worlds">
        {{world}}
        <button @click="worlds.splice(i, 1)">Zap!</button>
      </li>
    </ul>
    <input v-model="newWorld"/>
    <button @click="worlds.push(newWorld)">Conquer</button>
  </div>

  <script>
    new Vue({
      el: '#app',
      data: {
        worlds: ['Terran', 'L24-D', 'Ares', 'New Kroy', 'Sebek', 'Vestra']
      }
    })
  </script>
</body>
</html>
```


La web funciona, però què ens mostra la _consola_?

Solució: declarar `newWorld` a la instància de Vue:

```JavaScript
new Vue({
  el: '#app',
  data: {
    worlds: ['Terran', 'L24-D', 'Ares', 'New Kroy', 'Sebek', 'Vestra'],
    newWorld: ''
  }
})
```

Abreviacions
-------------

El caràcter `@` de `@click` [és una abreviació](https://vuejs.org/v2/guide/syntax.html#v-on-Shorthand) de la directiva `v-on:`


Per tant, 
```JavaScript
<button @click="worlds.push(newWorld)">Conquer</button>
```
és el mateix que
```JavaScript
<button v-on:click="worlds.push(newWorld)">Conquer</button>
```

Una altra directiva molt utilitzada, `v-bind:`, es pot abreviar amb `:`


{% endraw %}