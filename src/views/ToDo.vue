<template>
  <h1>TODO app</h1>
  <new-todo-form/>
  
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
import { Vue, Options } from "vue-class-component";
import NewTodoForm from "../components/NewTodoForm.vue"

@Options({
  components: {
    NewTodoForm
  }
})
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
