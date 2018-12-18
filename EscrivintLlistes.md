Escrivint llistes
==============

{% raw %}

Rang de números
-------------


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
      <li v-for="n in 4">Hello!</li>
    </ul>
  </div>


  <script>
    new Vue({
      el: '#app'
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
      <li v-for="n in 10">{{11-n}}</li>
      <li>launch missile!</li>
    </ul>
  </div>


  <script>
    new Vue({
      el: '#app'
    })
  </script>
</body>

</html>
```

Perquè `11-n`? Perquè Vue comença els índexos en 1.

Arrays
---------

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
      <li v-for="n in [10,9,8,7,6,5,4,3,2,1]">{{n}}</li>
      <li>launch missile!</li>
    </ul>
  </div>


  <script>
    new Vue({
      el: '#app'
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
      <li v-for="n in countdown">{{n}}</li>
      <li>launch missile!</li>
    </ul>
  </div>


  <script>
    new Vue({
      el:'#app',
      data: {
        countdown: [10,9,8,7,6,5,4,3,2,1]
      }
    })
  </script>
</body>

</html>
```

### Arrays amb notació d'índex

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
      <li v-for="(animal, i) in animals">
        The {{animal}} goes {{sounds[i]}}
      </li>
    </ul>
  </div>


  <script>
    new Vue({
      el: '#app',
      data: {
        animals: ['dog', 'cat', 'bird'],
        sounds: ['woof', 'meow', 'tweet']
      }
    })
  </script>
</body>

</html>
```

### Objectes

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
      <li v-for="(sound, name) in animals">
        The {{name}} goes {{sound}}
      </li>
    </ul>
  </div>


  <script>
    new Vue({
      el: '#app',
      data: {
        animals: {
          dog: 'woof', cat: 'meow', bird: 'tweet'
        }
      }
    })
  </script>
</body>

</html>
```

En aquest cas, no es garanteix que l'ordre del recorregut als atributs de l'objecte sigui el mateix en el que està escrit.

{% endraw %}