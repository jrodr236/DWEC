Introducció a Node.js
=====================

Node.js es un entorn d'execució para JavaScript.

Amb Node.js es poden programar pàgines web des del costat del servidor amb JavaScript.

https://nodejs.org/ca/

![node.js](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d9/Node.js_logo.svg/1280px-Node.js_logo.svg.png)

npm
---

npm és el gestor de paquets de JavaScript, integrat a Node.js

Es va dissenyar per poder utilitzar paquets de JavaScript i integrar-los en les nostres aplicacions de forma senzilla, com si fos un puzzle.

Ara mateix, npm és el registre d'aplicacions més gran del mon.

![npm](https://upload.wikimedia.org/wikipedia/commons/thumb/d/db/Npm-logo.svg/1200px-Npm-logo.svg.png)

Instal·lació de Node.js
----------------------

* Descarregar i instal·lar de la web oficial:

  https://nodejs.org/ca/

* Comprovar versions:

  ```
  node --version

  npm --version
  ```

Instal·lar vue-cli
------------------

https://cli.vuejs.org/

Vue Cli és la eina integrada a Node.js per desenvolupar amb Vue.js.

Instal·lem-la globalment:

```
npm install @vue/cli -g
```

Comprovem la versió

```
vue -- version
```

Fixa't que, fins ara, utilitzàvem una versió anterior: https://unpkg.com/vue/dist/vue.js

Crear projecte
--------------

vue create prova_vuejs

```
> default (babel, eslint)
```

cd prova_vuejs

npm run serve


Estructura: components
----------------------

Quan hem de treballar amb projectes grans, es recomana utilitzar components.

Els components son instàncies de Vue reutilitzables.

Fem un cop d'ull a la plantilla creada:
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

Nou component
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

Crearem un component

### App.vue

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
* 