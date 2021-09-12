<template>
    <form >
    <div class="input-group">
      <input  type="text" v-model="inputValue"  class="form-control"/>
      <button @click="addToDo" class="btn btn-primary input-group-append">Add</button>
    </div>
  </form>
</template>

<script lang="ts">
import { Vue } from 'vue-class-component'

export default class NewTodoForm extends Vue {

}
</script>
