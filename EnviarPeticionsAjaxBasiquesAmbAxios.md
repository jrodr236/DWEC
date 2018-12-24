Enviant peticions AJAX bàsiques amb Axios
=========================================

**Axios** és la llibreria recomenada per fer peticions HTTP a Vue. Permet dur a terme operacions utilitzant el patró REST de forma senzilla. Permet treballar amb concurrència, generant diverses sol·licituds al mateix temps.

Exemple
---------

```html
<!DOCTYPE html>
<html>
<head>
  <title>Advice of the day</title>
  <script src="https://unpkg.com/vue/dist/vue.js"></script>
  <script src="https://unpkg.com/axios/dist/axios.js"></script>
</head>
<body>
  <div id="app">
    <h2>Advice of the day</h2>
    <p>{{advice}}</p>
  </div>

  <script>
    new Vue({
      el: '#app',
      data: {
        advice: 'loading...'
      },
      created () {
        axios.get('http://api.adviceslip.com/advice')
        .then(response => {
          this.advice = response.data.slip.advice
        })
        .catch(error => {
          this.advice = 'There was an error: ' + error.message
        })
      }
    })
  </script>
</body>
</html>
```

Solucionar error
------------------

Aquest codi mostra un error, degut a que la web i les dades (API REST) estan a servidors diferents.

Per solucionar-ho, es pot instal·lar l'extensió de Chrome [Allow-Control-Allow-Origin: *](https://chrome.google.com/webstore/detail/allow-control-allow-origi/nlfbmbojpeacfghkpbjhddihlkkiljbi?hl=en-US).

Petició GET
------------

Fixe'm-nos que l'exemple fa una petició GET a https://api.adviceslip.com/advice. Si visitem aquesta URL, ens retorna un JSON amb l'advice:

```
{"slip": {"advice":"Big things have small beginnings.","slip_id":"163"}}
```

Indentem el JSON:

```
{
    "slip": {
        "advice":"Big things have small beginnings.",
        "slip_id":"163"
    }
}
```

L'exemple recull la frase a la següent sentència:

```
this.advice = response.data.slip.advice
```

Mètode `created()`
--------

El mètode `created()` s'executa quan es crea la instància de Vue, és a dir, quan arrenca l'aplicació.

Crida assíncrona
---------------

La següent sentència:

```JavaScript
axios.get('http://api.adviceslip.com/advice')
.then(response => {
    this.advice = response.data.slip.advice
})
.catch(error => {
    this.advice = 'There was an error: ' + error.message
})
```

Què fa?

1. Fa la crida HTTP GET contra la URI indicada.
2. Continua, sense esperar a rebre resposta, retornant una _Promise_.

Les _Promises_ ens permet realitzar crides assíncrones. Si la crida es realitzes de forma síncrona, l'aplicació web es quedaria bloquejada esperant la resposta.

Quan la resposta arribi, executarà l'_arrow function_ que s'ha passat per paràmetre

```JavaScript
response => {
    this.advice = response.data.slip.advice
}
```

Les _arrow function_ son funcions sense nom, amb una sintaxi més curta que les funcions convencionals.

En cas que es produeixi un error, s'executa

```JavaScript
error => {
    this.advice = 'There was an error: ' + error.message
}
```

Podem tornar a generar un error desactivant l'extensió anterior, o desconnectant la xarxa.