Crear un client i un servidor REST
==================================

{% raw %}

Servidor REST
-------------
Utilitzarem _Feather.js_ per crear un servidor REST.

A una màquina amb Node.js instal·lat, fer:

```
npm install -g @feathersjs/cli
mkdir my-server
cd my-server
feathers generate app
```
respondre valors per defecte

```
feathers generate service
```

a la pregunta sobre el nom del _resource_, escollir **messages**

```
npm start
```

Obrir un navegador i consultar el port 3030.
- http://localhost:3030/
- http://localhost:3030/messages

```html
<!DOCTYPE html>
<html>
<head>
  <title>Sticky messages</title>
  <script src="https://unpkg.com/vue/dist/vue.js"></script>
  <script src="https://unpkg.com/axios/dist/axios.js"></script>
</head>
<body>
  <div id="app">
    <h3>Sticky messages</h3>
    <ol>
      <li v-for="message in messages">
        <button @click="deleteItem(message._id)">Delete</button>
        <button @click="edit(message._id, message.text)">edit</button>
        <input v-model="message.text">
      </li>
    </ol>
    <input v-model="toAdd">
    <button @click="add">add</button>
  </div>

  <script>
    new Vue({
      el: '#app',
      data: {
        messages: [],
        toAdd: ''
      },
      created () {
        axios.get('http://localhost:3030/messages/')
          .then(response => {
            this.messages = response.data.data
          })
      },
      methods: {
        deleteItem (id) {
          axios.delete('http://localhost:3030/messages/' + id)
            .then(response => {
              if (response.status < 400) {
                this.messages.splice(this.messages.findIndex(e => e._id === id), 1)
              }
            })
        },
        add () {
          axios.post('http://localhost:3030/messages/', {
            text: this.toAdd
          })
            .then(response => {
              if (response.status === 201) {
                this.messages.push(response.data)
              }
            })
        },
        edit (id, text) {
          axios.put('http://localhost:3030/messages/' + id, {
            text
          })
            .then(response => {
              if (response.status < 400) {
                console.info(response.status)
              }
            })
        }
      }
    })
  </script>
</body>
</html>
```

L'html té els elements necessaris per veure, afegir, modificar i eliminar missatges.

La instància de `Vue` consisteix en els missatges emmagatzemats, i un missatge temporal preparat per afegir-lo a la llista.

A `created()` es demana al servidor la llista dels missatges.

Quan es crea un nou missage (mètode `add()`), s'envia al servidor.

L'eliminació d'un missatge (mètode `delete()`) i la edició (mètode `edit()`) funcionen de forma similar.

Podem comprovar que realment ens comuniquem amb el servidor refrescant la pàgina, o tancant i tornant a obrir el servidor, i comprovar que els missatges encara hi son.

Recordem els _verbs_ del protocol HTTP i les accions que es produeixen a REST:

- GET: retorna la representació del recurs
- POST: puja un nou recurs
- PUT: puja un recurs existent (per modificar-lo)
- DELETE: elimina un recurs

Axios utilitza els verbs d'HTTP per anomenar els seus mètodes.

{% endraw %}