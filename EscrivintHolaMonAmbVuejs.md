Escrivint Hola Mon amb Vue.js
========================

`new Vue({el:'#app'})` instanciarà una nova instància de `Vue`.

El paràmetre `#app` és un selector que retornarà l'element de la pàgina amb l'identificador `app`.

```html
<!DOCTYPE html>
<html>
<head>
  <title></title>
  <script src="https://unpkg.com/vue/dist/vue.js"></script>
</head>
<body>
  <div id="app">
    {{'Hello ' + 'world'}}

    \{
      
    \{\{
  </div>

  <script>
    new Vue({el:'#app'})
  </script>
</body>
</html>
```

```html
<!DOCTYPE html>
<html>
<head>
  <title></title>
  <script src="https://unpkg.com/vue/dist/vue.js"></script>
</head>
<body>
  <div id="app">
    We conquered {{countWorlds}} planets.<br/>
    Hello {{countWorlds}} worlds
  </div>
  <script>
    new Vue({
      el:'#app',
      data: {
        countWorlds: 5 + 2
      }
    })
  </script>
</body>
</html>
```