<template>
  <h1>TODO app</h1>
  <new-todo-form @onSubmittedTodo="appendToDo"/>
  
  <div>
    <ul  v-for="(todo, index) in todos" :key="index" class="list-group">
      <li class="list-group-item">
        <label for="">{{todo}}</label>
        <button @click="removeTodo(index)" class="btn btn-danger btn-sm">
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

  public appendToDo (todo:string){
    this.todos.push(todo)
  }

  public removeTodo(index: number){
    this.todos.splice(index, 1)
  }
}
</script>
