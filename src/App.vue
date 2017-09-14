<template>
  <div id="app">
    <h1>Todolist</h1>
    <input type="text" v-model="entry" @keyup.enter="addTodo"/>
    <div>
      <div v-for="(todo,index) in todos" v-bind:key="index">{{todo}} {{index}}</div>
    </div>
    <h1>{{parentMsg}}</h1>
    <input type="text" v-model="parentMsg">
    <todo-entry v-bind:my-message="parentMsg" ></todo-entry>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import Component from 'vue-class-component';
import TodoEntry from './TodoEntry.vue';
@Component({
    components: {
        "todo-entry": TodoEntry
    }
})
export default class App extends Vue {
  todos: string[] = ['todo1','todo2']
  entry: string = ''
  parentMsg : string = 'This message from parent'
  addTodo() {
    this.todos.push(this.entry)
  }

}

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
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
