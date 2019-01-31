Enviar dades a un servidor
======================

{% raw %}

Imaginem que tenim un _blog_ i volem escriure una nova _entrada_.

Com que no tenim cap servidor per enviar l'_entrada_, treballarem amb un servei molt útil: Typicode. Bàsicament és un _fake REST server_. Enviarem una petició i el servidor respondrà d'una manera realista, encara que no passi res en realitat.

Utilitzant Axios
---------------

```html
<!DOCTYPE html>
<html>
<head>
  <title>Enviar dades</title>
  <script src="https://unpkg.com/vue/dist/vue.js"></script>
  <script src="https://unpkg.com/axios/dist/axios.js"></script>
</head>
<body>
  <div id="app">
    <h3>Write a new post</h3>
    <form>
      <div>
        <label>Title of your post:</label>
        <input type="text" v-model="title">
      </div>
      <div>
        <label>Write your thoughts for the day</label>
        <textarea v-model="body"></textarea>
      </div>
      <div>
        <button @click.prevent="submit">Submit</button>
      </div>
    </form>
    <h3>Rensponse from the server</h3>
    <pre>{{response}}</pre>
  </div>

  <script>
    new Vue({
      el: '#app',
      data: {
        userId: 1,
        title: '',
        body: '',
        response: '...'
      },
      methods: {
        submit () {
          axios.post('http://jsonplaceholder.typicode.com/posts', {
            title: this.title,
            body: this.body,
            userId: this.userId
          }).then(response => {
            this.response = JSON.stringify(response,null,' ')
          }).catch(error => {
            this.response = 'Error: ' + error.response.status
          })
        }
      }
    })
  </script>
</body>
</html>
```

El mètode `post` serveix per modificar les dades del servidor.

Quan s'envia l'_entrada_, el servidor repeteix l'_entrada_ i contesta amb el seu ID.

```
{
 "data": {
  "title": "Títol",
  "body": "Pensaments",
  "userId": 1,
  "id": 101
 },
 ...
 ```

Utilitzant objectes natius del navegador
-------------------------------

Es mostra a continuació el codi equivalent utilitzant els objectes natius del navegador. Fixe'm-nos que, utilitzant la llibreria Axios, el codi és molt més concís i expressiu.

```html
<!DOCTYPE html>
<html>
<head>
  <title>Enviar dades</title>
  <script src="https://unpkg.com/vue/dist/vue.js"></script>
</head>
<body>
  <div id="app">
    <h3>Write a new post</h3>
    <form>
      <div>
        <label>Title of your post:</label>
        <input type="text" v-model="title">
      </div>
      <div>
        <label>Write your thoughts for the day</label>
        <textarea v-model="body"></textarea>
      </div>
      <div>
        <button @click.prevent="submit">Submit</button>
      </div>
    </form>
    <h3>Rensponse from the server</h3>
    <pre>{{response}}</pre>
  </div>

  <script>
    new Vue({
      el: '#app',
      data: {
        userId: 1,
        title: '',
        body: '',
        response: '...'
      },
      methods: {
        submit () {
          const xhr = new XMLHttpRequest()
          xhr.open('post', 'http://jsonplaceholder.typicode.com/posts')
          xhr.setRequestHeader('Content-Type', 'application/json;charset=UTF-8')
          xhr.onreadystatechange = () => {
            const DONE = 4
            const CREATED = 201
            if (xhr.readyState === DONE) {
              if (xhr.status === CREATED) {
                this.response = xhr.response
              } else {
                this.response = 'Error: ' + xhr.status
              }
            }
          }
          xhr.send(JSON.stringify({
            title: this.title,
            body: this.body,
            userId: this.userId
          }))
        }
      }
    })
  </script>
</body>
</html>
```

{% endraw %}