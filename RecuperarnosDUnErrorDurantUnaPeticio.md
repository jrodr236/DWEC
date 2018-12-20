Recuperar-nos d'un error durant una petició
=======================================

Crearem un web per demanar pizzes des de la muntanya de l'Everest. Com que tenen una connexió a Internet força dolenta, s'haura de repetir la petició vàries vegades abans de donar-nos per veçuts respecte a la pizza.

```html
<!DOCTYPE html>
<html>
<head>
  <title>Pizza</title>
  <script src="https://unpkg.com/vue/dist/vue.js"></script>
  <script src="https://unpkg.com/axios/dist/axios.js"></script>
  <style>
    @keyframes spin {
        100% {transform:rotate(360deg);}
    }
    .spinner {
        width: 1em;
        height: 1em;
        padding-bottom: 12px;
        display: inline-block;
        animation: spin 2s linear infinite;
    }
  </style>
</head>
<body>
  <div id="app">
    <h3>Everest pizza delivery</h3>
    <button @click="order" :disabled="inProgress">Order pizza!</button>
    <span class="spinner" v-show="inProgress">🍕</span>
    <h4>Pizza wanted</h4>
    <p>{{requests}}</p>
    <h4>Pizzas ordered</h4>
    <span v-for="pizza in responses">{{pizza.id}}:{{pizza.req}}</span>
  </div>

  <script>
    new Vue({
      el: '#app',
      data: {
        inProgress: false,
        requests: new Object(null),
        responses: new Object(null),
        counter: 0,
        impatientAxios: undefined
      },
      created () {
        this.impatientAxios = axios.create({
          timeout: 3000 
        })
      },
      methods: {
        order (event, oldRequest) {
          let request = undefined
          if (oldRequest) {
            request = oldRequest
          } else {
            request = { req: '🍕', id: this.counter++}
          }
          this.inProgress = true
          this.requests[request.id] = request
          this.impatientAxios.get('http://httpstat.us/200')
          .then(response => {
            this.inProgress = false
            this.responses[request.id] = this.requests[request.id]
            delete this.requests[request.id]
          })
          .catch(e => {
            this.inProgress = false
            console.error(e.message)
            console.error(this.requests.s)
            setTimeout(this.order(event, request), 1000)
          })
        }
      }
    })
  </script>
</body>
</html>
```

Per les peticions (`requests`) i les respostes (`responses`) estaria bé utilitzar els `Set` de JavaScript, però no son reactius a Vue. Per això utilitzem objectes, que inicialitzem com objectes buits.


Normalment, Axios espera mentre el navegador esperi la resposta. Com que estem impacients, creem la variable `impatientAxios` per que deixi anar la connexió després de 3 segons.

Al mètode `order`, utilitzem http://httpstat.us/200 que, simplement, respon 200 OK a totes les nostres peticions.

Ara simularem una connexió lenta:
1. Obre les _Developer Tools_ del Chrome (F12)
2. Escull la pestanya _Network_
3. Fes clic a _Online_ i escull _Add_
4. Afegeix un nou _throttling_ (acceleració) anomenat Everest, amb 1kb/s de pujada i baixada, i 1000ms de latència.

Si no funciona cap petició de pizza, variar els paràmetres de Everest.

Hi ha moltes maneres d'enfrontar-se a connexions lentes o inestables, i hi ha moltes biblioteques que s'integren amb Axios (com Patience JS), que tenen estratègies més avançades per reenviar peticions i son senzilles d'utilitzar.

