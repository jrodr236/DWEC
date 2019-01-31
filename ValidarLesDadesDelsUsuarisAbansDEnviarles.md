Validar les dades dels usuaris abans d'enviar-les
========================================

{% raw %}

```html
<!DOCTYPE html>
<html>
<head>
  <title>Validar</title>
  <script src="https://unpkg.com/vue/dist/vue.js"></script>
  <script src="https://unpkg.com/axios/dist/axios.js"></script>
</head>
<body>
  <div id="app">
    <form @submit="vueSubmit">
      <div>
        <label>Name</label>
        <input type="text" required>
      </div>
      <div>
        <label>Email</label>
        <input type="email" required>
      </div>
      <div>
        <label>Submit</label>
        <button type="submit">Submit</button>
      </div>
    </form>
  </div>

  <script>
    new Vue({
      el: '#app',
      methods: {
        vueSubmit() {
          console.info('fake AJAX request')
        }
      }
    })
  </script>
</body>
</html>
```

`required` i `type="email"` permet validar l'entrada de l'usuari utilitzant html5.

Però la directiva `@submit` (equivalent a `v-on:submit`) no crida la validació nativa de les dades i el formulari sempre s'envia. Aquest problema se soluciona amb la directiva `@submit.prevent`:

```html
<!DOCTYPE html>
<html>
<head>
  <title>Validar</title>
  <script src="https://unpkg.com/vue/dist/vue.js"></script>
  <script src="https://unpkg.com/axios/dist/axios.js"></script>
</head>
<body>
  <div id="app">
    <form @submit.prevent="vueSubmit">
      <div>
        <label>Name</label>
        <input type="text" required>
      </div>
      <div>
        <label>Email</label>
        <input type="email" required>
      </div>
      <div>
        <label>Submit</label>
        <button type="submit">Submit</button>
      </div>
    </form>
  </div>

  <script>
    new Vue({
      el: '#app',
      methods: {
        vueSubmit() {
          console.info('fake AJAX request')
        }
      }
    })
  </script>
</body>
</html>
```

Creació de funcions
-------------------

Fixa't que, en l'exemple anterior, es mostra com es poden crear funcions a Vue: a dins l'atribut `methods` de la instància de `Vue`.

{% endraw %}