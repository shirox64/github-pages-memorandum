# Vue.js

## 0. Hello World!
```html
<html>
    <head>
    </head>
    <body>
        <div id="app">
          {{ message }}
        </div>

        <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
        <script src="sample.js"></script>
    </body>
</html>
```

```javascript
var app = new Vue({
  el: '#app',
  data: {
    message: 'Hello Vue!'
  }
})
```

## 1. if
```html
<html>
    <head>
    </head>
    <body>
        <div id="app">
          <span v-if="seen">TEST!!!</span>
        </div>

        <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
        <script src="sample.js"></script>
    </body>
</html>
```

```javascript
var app = new Vue({
  el: '#app',
  data: {
    seen: true
  }
})
```

## 2. for
```html
<html>
    <head>
    </head>
    <body>
        <div id="app">
          <ol>
            <li v-for="todo in todos">
                {{ todo.text }}
            </li>
          </ol>
        </div>

        <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
        <script src="sample.js"></script>
    </body>
</html>
```

```javascript
var app = new Vue({
  el: '#app',
  data: {
    todos: [
      {text: 'Learn JavaScript'},
      {text: 'Learn Vue'},
      {text: 'Build something awesome'}
    ]
  }
})
```

## 3. on
```html
<html>
    <head>
    </head>
    <body>
        <div id="app">
          <p>{{ message }}</p>
          <button v-on:click="reverseMessage">Reverse Message</button>
        </div>

        <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
        <script src="sample.js"></script>
    </body>
</html>
```

```javascript
var app = new Vue({
  el: '#app',
  data: {
    message: 'Hello Vue.js'
  },
  methods: {
    reverseMessage: function() {
      this.message = this.message.split('').reverse().join('')
    }
  }
})
```

## 4. model
```html
<html>
    <head>
    </head>
    <body>
        <div id="app">
          <p>{{ message }}</p>
          <input v-model='message'></input>
        </div>

        <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
        <script src="sample.js"></script>
    </body>
</html>
```

```javascript
var app = new Vue({
  el: '#app',
  data: {
    message: 'Hello Vue.js'
  }
})
```

## 5. component
```html
<html>
    <head>
    </head>
    <body>
        <div id="app">
          <todo-item
            v-for="item in groceryList"
            v-bind:todo="item">
          </todo-item>
        </div>

        <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
        <script src="sample.js"></script>
    </body>
</html>
```

```javascript
Vue.component('todo-item', {
  props: ['todo'],
  template: '<li>{{ todo.text }}</li>'
})

var app = new Vue({
  el: '#app',
  data: {
    groceryList: [
      {id: 0, text: 'Vegetables'},
      {id: 1, text: 'Cheese'},
      {id: 2, text: 'Whatever else humans are supposed to eat'}
    ]
  }
})
```