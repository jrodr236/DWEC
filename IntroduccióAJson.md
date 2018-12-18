Introducció a JSON
==================

JSON: _**J**ava**S**cript **O**bject **N**otation_

JSON és una sintaxi per emmgatzemar i intercanviar dades.

JSON és en format text (String), escrit amb notació d'objectes de JavaScript.

Intercanvi de dades
-------------------

Quan s'intercanvien dades entre un navegador i un servidor, les dades només poden ser de text.

Podem convertir qualsevol objecte JavaScript en JSON i enviar-ho al servidor.

També podem convertir qualsevol JSON rebut del servidor en objectes JavaScript.

D'aquesta manera, podem treballar amb dades com a objectes de JavaScript, sense cap anàlisi ni traduccions complicades.

Enviament de dades
-------------------

El mètode `JSON.stringify()` permet convertir un objecte Javascript en una cadena _(string)_ JSON, preparada per enviar-la a un servidor web.

[Exemple](https://www.w3schools.com/js/tryit.asp?filename=tryjson_send)

Recepció de dades
----------------

El mètode `JSON.parse()` permet convertir els cadenes _(strings)_ JSON rebudes del servidor web en un objecte JavaScript.

[Exemple](https://www.w3schools.com/js/tryit.asp?filename=tryjson_receive)

Regles de sintaxi de JSON
-------------------------

* Les dades estan en parelles de nom / valor
  ```JSON
  { "name":"John" }
  ```
* Les dades estan separades per comes `,`
  ```JSON
  { "name":"John", "age":30, "city":"New York" };
  ```
* Els objectes es posen entre claus `{}`
  ```JSON
  {
    "employee":{ "name":"John", "age":30, "city":"New York" }
  }
  ```
* Els arrays es posen entre claudators `[]`
  ```JSON
  {
    "employees":[ "John", "Anna", "Peter" ]
  }
  ```

[w3schools.com](https://www.w3schools.com/js/default.asp) > Secció `JS JSON`.