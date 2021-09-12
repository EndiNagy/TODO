<template>
    <form @submit.prevent="onSubmit">
    <div class="input-group">
      <input  type="text" v-model="newTodo" placeholder="Create new todo"  class="form-control"/>
      <button type="submit" class="btn btn-primary input-group-append">Add</button>
    </div>
  </form>
</template>

<script lang="ts">
import { Vue } from 'vue-class-component'

export default class NewTodoForm extends Vue {
    newTodo = ""

    public onSubmit(){
      if(this.newTodo){
        console.log(`Submitting new todo item: '${this.newTodo}'`)
        this.$emit("onSubmittedTodo", this.newTodo)
        this.newTodo = ""
        }
    }
}
</script>
