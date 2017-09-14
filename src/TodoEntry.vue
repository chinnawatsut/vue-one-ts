<template>

    <div id="todoEntry">
        <h1 @click="changeMessage">{{myMessage}}</h1>
        <input type="text" v-model="myMessage">
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Component from 'vue-class-component'

@Component({
    props: {
    myMessage: String
  }
})
export default class TodoEntry extends Vue{

}
</script>

<style>

</style>
