<template>
  <div class="hello">
    <span v-bind:title="message">
      Hover your mouse over me for a few seconds to see my dynamically bound title!
    </span>
    <br>

    <span v-if="seen">Now you see me</span>
    <br>

    <ol>
      <li v-for="todo in todos" :key="todo.text">
        {{ todo.text }}
      </li>
    </ol>
    <br>

    <button v-on:click="reverseMessage">Reverse Message</button>
    <br>

    <p>{{ twoWayBinding }}</p>
    <input v-model="twoWayBinding">
    <br>

    <ChildComponent
      v-for="item in groceryList"
      v-bind:todo="item"
      v-bind:key="item.id"
    />
  </div>
</template>

<script>
    import ChildComponent from './ChildComponent';

    export default {
    name: 'hello-world',
    components: {
      ChildComponent
    },
    data: function () {
        return {
            message: 'You loaded this page on ' + new Date().toLocaleDateString(),
            seen: true,
            todos: [
                { text: 'Learn Javascript' },
                { text: 'Learn Vue' },
                { text: 'Build something awesome' },
            ],
            twoWayBinding: 'Two way binding',
            groceryList: [
                { id: 0, text: 'Vegetables' },
                { id: 1, text: 'Cheese' },
                { id: 2, text: 'Whatever else humans are supposed to eat' }
            ],
        }
    },
    methods: {
        reverseMessage: function () {
          this.message = this.message.split('').reverse().join('')
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
