<template>
  <h1>TODO app</h1>
  <form >
    <div class="input-group">
      <input  type="text" v-model="inputValue"  class="form-control"/>
      <button @click="addToDo" class="btn btn-primary input-group-append">Add</button>
    </div>
  </form>
  <div>
    <ul  v-for="todo in todos" :key="todo" class="list-group">
      <li class="list-group-item">
        <label for="">{{todo}}</label>
        <button @click="removeTodo" class="btn btn-danger btn-sm">
          <i class="bi bi-x-lg"/>
        </button>
      </li>
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
</style>
