<template>
  <h1>TODO app</h1>
  <div class="todo-card">
    <input  type="text" v-model="inputValue" />
    <button @click="addToDo">Add</button>
    <ul id="todo-list" v-for="todo in todos" :key="todo">
      <li>{{todo}}</li>
      <button @click="removeTodo">X</button>
    </ul>
  </div>
</template>
<script lang="ts">
import { Vue } from "vue-class-component";

export default class ToDo extends Vue {
  inputValue = "Note ToDo here"
  todos: string[] = ["Be awesome", "Work out"]

  public addToDo (){
    if (this.inputValue){
      //this.$emit("add-todo", this.inputValue)

      console.log(`˙Adding ${this.inputValue}`)
      this.todos.push(this.inputValue)
      this.inputValue = ""
    }
  }
  public removeTodo(){
    console.log(`Remove `)
  }
}
</script>

<style scoped>
#todo-list{
  border: #2c3e50 solid;
  width: auto;
  text-align: center;
}
</style>
