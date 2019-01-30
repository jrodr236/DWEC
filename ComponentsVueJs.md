Components de Vue.js
=======

![The evolution of software architecture](http://eye8.me/2016/06/30/Educational-Microservice/pasta.jpg)

Quan hem de treballar amb projectes grans, es recomana utilitzar components.

Els components son instàncies de Vue reutilitzables.

Fem un cop d'ull a l'estructura de la nova aplicació:
- A public/index.html hi ha la pàgina html principal.
  - Aquesta pàgina no conté un enllaç a la biblioteca de Vue.js, perquè és un mòdul integrat en el nostre Node.js
  - Hi ha un enllaç al component `app`

    `<div id="app"></div>`
- a src/App.vue hi ha un component
  - `<template>`: codi html
  - `<script>`: codi javascript/vue
  - `<style>`: estils CSS

  Aquest component conté, a dins un altre component: ./components/HelloWorld.vue
- components/HelloWorld.vue té la mateixa estructura

Crear un nou component
--------------

A partir de l'exemple que ja vam veure:

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

Crearem un component (fitxer `App.vue`)

```html
<template>
  <div id="app">
    <ul>
      <li v-for="(world, i) in worlds" v-bind:key="i">
        {{world}}
        <button @click="worlds.splice(i, 1)">Zap!</button>
      </li>
    </ul>
    <input v-model="newWorld"/>
    <button @click="worlds.push(newWorld)">Conquer</button>
  </div>
</template>

<script>
  export default {
    name: 'app',
    data: function() {
      return {
        worlds: ['Terran', 'L24-D', 'Ares', 'New Kroy', 'Sebek', 'Vestra'],
        newWorld: ''
      }
    }
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
```

Canvis:
* A la versió 3.X de Vue.js, cal afegir la clau de cada entrada als `v-for` (`v-bind:key`).
* Dins un component, `data` ha de ser una funció.