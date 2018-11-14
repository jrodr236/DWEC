Formatejant el text amb filtres
================

{% raw %}

```html
<!DOCTYPE html>
<html>
<head>
  <title></title>
  <script src="https://unpkg.com/vue/dist/vue.js"></script>
</head>
<body>
  <div id="app">
    {{'hello world' | capitalize }}
  </div>

  <script>
    Vue.filter('capitalize', function (string) {
      var capitalFirst = string.charAt(0).toUpperCase()
      var noCaseTail = string.slice(1, string.length)
      return capitalFirst + noCaseTail
    })
    new Vue({el:'#app'})
  </script>
</body>
</html>
```

Provem de fer el mateix però utilitzant ECMAScript 6:

```html
<!DOCTYPE html>
<html>
<head>
  <title></title>
  <script src="https://unpkg.com/vue/dist/vue.js"></script>
</head>
<body>
  <div id="app">
    {{'hello world' | capitalize }}
  </div>

  <script>
    Vue.filter('capitalize', function (string) {
      var [first, ...tail] = string
      return first.toUpperCase() + tail.join('')
    })
    new Vue({el:'#app'})
  </script>
</body>
</html>
```

Explicació:

> The second line is called a
destructuring assignment of string; in particular we are interpreting string as an array of
characters, separating the first character into first and putting all the other characters in
tail. This is a faster way to assign different parts of an array to multiple variables. 

> The
other thing that may seems mysterious is that join(''). Since tail is now an array of
characters, we need some means to re-join the single letters into a compact string. The
argument of join represents a separator between the single characters. We don't want any,
so we pass an empty string.

{% endraw %}