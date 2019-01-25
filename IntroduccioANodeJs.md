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
vue --version
```

Fixa't que, fins ara, utilitzàvem una versió anterior: https://unpkg.com/vue/dist/vue.js

Crear projecte
--------------
```
vue create prova_vuejs
```
Escollir la opció per defecte:
```
> default (babel, eslint)
```

Entrar al directori creat i iniciar el servidor:
```
cd prova_vuejs
npm run serve
```
