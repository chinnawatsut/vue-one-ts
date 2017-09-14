<template>
  <div id="app">

     <v-toolbar>
    <v-toolbar-title>Register</v-toolbar-title>
    <v-spacer></v-spacer>
    <v-toolbar-side-icon class="hidden-md-and-up"></v-toolbar-side-icon>
    <v-toolbar-items class="hidden-sm-and-down">
      <v-btn flat>Link One</v-btn>
      <v-btn flat>Link Two</v-btn>
      <v-btn flat>Link Three</v-btn>
    </v-toolbar-items>
  </v-toolbar>



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
import 'vuetify/dist/vuetify.min.css'

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
</style>
