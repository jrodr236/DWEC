Debugar aplicacions
================

A continuació veurem una forma ràpida i senzilla de veure el valor d'un objecte.

```html
<!DOCTYPE html>
<html>
<head>
  <title></title>
  <script src="https://unpkg.com/vue/dist/vue.js"></script>
</head>
<body>
  <div id="app">
    <p>Cat object: {{ cat }}</p>
  </div>

  <script>
    new Vue({
      el: '#app',
      data: {
        cat: {
          sound: 'meow'
        }
      }
    })
  </script>
</body>
</html>
```

Mostra l'objecte `cat` en format json. Cal vigilar utilitzar aquest tipus de _debug_, perquè si intentem mostrar un objecte amb referències circulars es provocarà un error. Qualsevol element HTML té referències al seu pare, i aquest alhora al seu fill.