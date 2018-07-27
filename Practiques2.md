Pràctiques bloc 2
================

Pràctiques preparatòries
-------------------
> Les següents pràctiques no s'avaluaran.

### Número més gran I

Has de crear una web que demani dos números a l’usuari i mostri en pantalla un missatge que digui quin dels dos números és
el més gran o si son iguals.

### Número més gran II

Modifica la web anterior de manera que tot el procés el faci una funció. La funció ha de rebre dos paràmetres (els números) i
ha de retornar el número més gran. Si són iguals ha de retornar el caràcter “x”. Cal mostrar els mateixos missatges que a
l’exercici anterior però utilitzant la nova funció creada.

### Quina edat tens? I

Has de crear una web que demani l’edat a l’usuari i mostri un missatge diferent segons la resposta:
* Fins a 18 anys cal informar a l’usuari que és menor d’edat.
* Entre els 18 i 65 l’usuari ha de saber que és un adult.
* Els usuaris majors de 65 estan a la segona joventut.

### Quina edat tens? II

Crea una web que demani l’edat de l’usuari i si aquesta edat és superior o igual als 18 anys també demani el nom a l’usuari. Cal mostrar en pantalla la informació obtinguda de l’usuari.

### Imatge

Crea una web que demani a un usuari si vol veure una imatge. En cas de que l’usuari respongui afirmativament s’ha de
mostrar una imatge qualsevol. En cas contrari s’ha de mostrar un missatge tipus: “Has decidit no veure la imatge”.

### Encapçalaments

Crea un script que escrigui en una pàgina web els encapçalaments desde `<h1>` fins a `<h6>`, amb un text que posi:
`encapçalament de nivell X`, on `X` és el nivell que estem escrivint.

###  Números del X al Y de N en N

Crea una web que demani tres números a l’usuari i mostri tots els números del rang triat per l’usuari amb els
dos primers números. S’ha de fer amb salts a partir del tercer número escollit per l’usuari.

Exemples:

```
Entrada
1, 10, 4

Sortida
1, 5, 9
```

```
Entrada
2, 20, 3

Sortida
2, 4, 7, 10, 13, 16, 19
```

###  Números del X al Y al revés

Crea una web que demani dos números a l’usuari i mostri tots els números del rang escollit per l’usuari sentit descendent.

Calculadora *especial*
----------------------
> Aquesta pràctica s'haurà de lliurar i s'avaluarà.

Crea una pàgina web que sigui una calculadora *especial*.

Haurà de complir els següents requeriments:
1. Ha de permetre sumar, restar, multiplicar i dividir números.
2. Ha de permetre fer potències. S'ha d'implementar a base de multiplicacions.
3. Ha de permetre fer el factorial d'un número. S'ha d'implementar de forma recursiva.
4. Ha de permetre concatenar paraules.
5. Ha de permetre ordenar fins a 10 números. S'ha d'implementar utilitzant el mètode adient d'`Array`.
6. Ha de permetre eliminar els números negatius d'un conjunt de fins a 10 números. S'ha d'implementar utilitzant el mètode adient d'`Array`.
7. Ha de permetre sumar 1 dia a una data. Cal utilitzar la classe `Date`.
8. Ha de permetre obtenir l'arrel quadrada d'un número.
9. Ha de permetre obtenir un número aleatori entre dos números donats.
10. Ha de permetre fer les operacions lògiques AND, OR i NOT.

S'ha de verificar l'entrada de l'usuari. En cas que sigui incorrecta, mostrar un error.

Cadascuna de les operacions ha d'estar implementada en una funció. Les funcions han d'estar en un fitxer propi, separades del codi html.

Per aquesta pràctica, no et preocupis gaire pel disseny de la pàgina, centra't en que el codi JavaScript sigui correcte, fàcil d'entendre i amb un bon estil de programació.