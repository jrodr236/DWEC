Introducció a Javascript
======================

[Resum](https://gitpitch.com/jrodr236/DWEC/master?p=IntroduccioJavaScript)

Tecnologies web
--------------------
Fins ara heu treballat amb pàgines web estàtiques:
* Estàn allotjades a un servidor
* Des del client es descarrega la pàgina i es *renderitza* al navegador.

  ![client-servidor](https://www.tankonyvtar.hu/en/tartalom/tamop425/0027_ADW1/images/ADW100.png)

* Els llenguatges utilitzats son HTML (contingut) i CSS (format).

  ![html i css](https://www.imaginanet.com/thumb.php?n=blog%2F10herramientas.jpg&w=640&h=250&x=0&y=0)

Es poden aconseguir pàgines web dinàmiques si hi afegim estructures de programació. Però... a on s'executarà el codi, al navegador o al servidor

![front-end vs. back-end](https://s3-us-west-2.amazonaws.com/devcodepro/media/blog/frontend-y-backend.png)

### Front-end

Tecnologies que s'executen al costat del client (navegador).

El llenguatge utilitzat és el JavaScript.

![JavaScript](http://lineadecodigo.com/wp-content/uploads/2014/04/javascript.png)

### Back-end


Tecnologies que s'executen al servidor.

Alguns dels llenguatges més utilitzats: PHP, JavaScript (utilitzant Node.js), Java, Python, .net, etc...

![llenguatges back-end](https://image.slidesharecdn.com/97d66a5b-e796-4247-b320-a623835d58f8-160630025826/95/computer-programming-for-lawyers-15-638.jpg?cb=1467292671)


Què és JavaScript?
---------------

JavaScript és el que es coneix com un llenguatge de script, es tracta de codi de programació inserit en un document.

Va ser desenvolupat per la empresa Netscape amb la idea de potenciar portals web dinàmiques amb navegador Netscape Navigator.

![Netscape](https://cdn.freebiesupply.com/logos/large/2x/netscape-1-logo-png-transparent.png)

JavaScript és interpretat directament pel navegador i per tant necessita accedir als elements HTML de la pàgina.

La definició del [MDN](https://developer.mozilla.org/ca/docs/Web/JavaScript) és:
> JavaScript® (tot sovint abreujat com a JS) és un llenguatge orientat a objectes, lleuger i interpretat, amb [funcions de primera classe](https://en.wikipedia.org/wiki/First-class_functions), més conegut per ser el llenguatge d'scripting per a pàgines Web, però també utilitzat en molts àmbits fora d'un navegador web com ara [node.js](http://nodejs.org/) o [Apache CouchDB](http://couchdb.apache.org/).

JavaScript i Java son llenguatges diferents, encara que tenen similituds en la sintaxi.

Història
---------
A principis dels anys 90 començaven a desenvolupar-se les primeres aplicacions web, i per tant les pàgines començaven a incloure formularis.

Amb unes aplicacions web cada cop més complexes i una velocitat de navegació lenta, va sorgir la necessitat d'un **llenguatge de programació que s'executés en el navegador** de l'usuari.

En cas que l'usuari no omplis correctament un formulari, no se’l feia esperar molt temps fins que el servidor tornés a mostrar el formulari indicant els errors existents.

**Brendan Eich**, un programador que treballava en Netscape, va pensar que podria solventar el problema adaptant altres tecnologies existents (com ScriptEase) al navegador Netscape Navigator 2.0.

![Brendan Eich](https://upload.wikimedia.org/wikipedia/commons/0/09/BEich.jpg)

![Netscape Navigator 2](https://udger.com/pub/img/ua_screenshots/netscape-2.02.png)

Inicialment Eich va anomenar al seu llenguatge **LiveScript** (1995).

Com a curiositat, dir que anys més tard Eich va ser un dels fundadors del projecte Mozilla, que va transformar el navegador Netscape en el Firefox, el primer gran projecte de canvi de codi privatiu a lliure.

Al mateix temps, **Microsoft** va llançar **JScript** amb **Internet Explorer 3**. JScript era una copia de JavaScript al que li van canviar el nom per evitar problemes legals.

![Internet Explorer 3](https://upload.wikimedia.org/wikipedia/it/9/93/Internet_Explorer_3.png)

Netscape va decidir estandaritzar el llenguatge JavaScript. El 1997 es va enviar la especificació JavaScript 1.1 al organisme ECMA (European Computer Manufacturers Association).

El primer estàndard que va crear ECMA es va denominar **ECMA-262**, en el que es va definir per primer cop el llenguatge **ECMAScript**.

JavaScript no es més que la implementació realitzada per Netscape del estàndar [ECMAScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Language_Resources).

ECMA ha publicat diferents edicions relacionades amb ECMAScript.

A data d’avui la gran majoria de navegadors suporten l’estàndard **ECMAScript 5.1**.

La última versió és **ECMAScript 9** publicada al Juny de 2018.
