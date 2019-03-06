Creant aplicacions en temps real amb Socket.IO
===================

{% raw %}

Les aplicacions modernes son el temps real, no en el sentit tradicional, sinò en el que no necessiten recarregar la pàgina per actualitzar-se. La forma més comuna per implementar això és amb WebSockets. El següent exemple utilitzarà Socket.io per fer un xat.

Instal·lació i configuració de Socket.IO
--------------------------

Crear un directori amb nom `xat-node`.
Hi afegirem els següents fitxers:
- package.json
- servidor-xat.js

### package.json

En aquest fitxer hi ha la configuració inicial:

```JSON
{
  "name": "exemple-socket-xat",
  "version": "0.0.1",
  "description": "la meva primera app socket.io",
  "dependencies": {}
}
```

Fixa't que, inicialment, no hi han dependències.


### servidor-xat.js

Aquesta és l'aplicació que gestionarà els missatges.

```JavaScript
var app = require('express')();
var http = require('http').Server(app);
var io = require('socket.io')(http);

io.on('connection', function(socket){

  console.log("S'ha connectat un usuari");

  socket.on('disconnect', function(){
    console.log("S'ha desconnectat un usuari");
  });

  socket.on('missatge de xat', function(msg){
    console.log('Missatge rebut: ' + msg);
    io.emit('missatge de xat', msg);
    //socket.broadcast.emit('missatge de xat', msg); //no inclou emissor
  });

});

http.listen(3000, function(){
  console.log('escoltant a *:3000');
});
```

### Configuració i execució del servidor

Dins del directori `xat-node`, executar les següents comandes:
```
npm install --save express@4.15.2
npm install --save socket.io
```

Després d'executar les comandes anteriors, s'han afegit les dependències instal·lades al fitxer de configuració `package.json`:

```JSON
{
  "name": "exemple-socket-xat",
  "version": "0.0.1",
  "description": "la meva primera app socket.io",
  "dependencies": {
    "express": "^4.15.2",
    "socket.io": "^2.2.0"
  }
}
```

Ara, arrenquem l'app:

```
node servidor-xat.js
```

Creació de la part web
--------------------

Crear un altre directori, anomenat `xat-vue`, i posar-hi els següents fitxers:

### xat.css

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font: 13px Helvetica, Arial;
}

form {
  background: #000;
  padding: 3px;
  position: fixed;
  bottom: 0;
  width: 100%;
}

form input {
  border: 0;
  padding: 10px;
  width: 90%;
  margin-right: .5%;
}

form button {
  width: 9%;
  background: rgb(130, 224, 255);
  border: none;
  padding: 10px;
}

#llistaMissatges {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

#llistaMissatges li {
  padding: 5px 10px;
}

#llistaMissatges li:nth-child(odd) {
  background: #eee;
}
```

### xat.html

```html
<!doctype html>
<html>

<head>
  <title>Xat Socket.IO</title>
  <link rel="stylesheet" type="text/css" href="xat.css">
</head>

<body>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/socket.io/2.2.0/socket.io.dev.js"></script>
  <script src="https://unpkg.com/vue/dist/vue.js"></script>

  <div id="app">
    <ul id="llistaMissatges">
      <li v-for="m in missatges">{{m}}</li>
    </ul>
    <form id="formulari">
      <input v-model="nouMissatge" autocomplete="off" />
      <button v-on:click="enviar()">Send</button>
    </form>
  </div>

  <script src="xat.js"></script>

</body>

</html>
```

### xat.js

```JavaScript
var socket = io('http://localhost:3000');

var vm1 = new Vue({
    el: '#app',
    methods: {
        enviar() {
            console.log('missatge a enviar: ', this.nouMissatge);
            socket.emit('missatge de xat', this.nouMissatge);
        }
    },
    data: {
        missatges: [],
        nouMissatge: ''
    }
})

socket.on('missatge de xat', function (msg) {
    console.log('missatge rebut: ', msg);
    vm1.missatges.push(msg);
    vm1.nouMissatge = '';
})

// prevents page reloading
document.getElementById("formulari").addEventListener("click", function (event) {
    event.preventDefault()
});
```

Obrim l'arxiu html vàries vegades, en dos o tres pestanyes d'un navegador web.

Podem comprovar que els missatges escrits en una de les pestanyes s'envia a les altres.

Ara caldria identificar les parts principals del codi:
- `servidor-xat.js`
  * Connexió d'un usuari
  * Desconnexió d'un usuari
  * recepció d'un missatge
  * reenviament del missatge a tothom, o exceptuant l'emissor
- `xat.js`
  * enviament d'un missatge
  * recepció d'un missatge

{% endraw %}