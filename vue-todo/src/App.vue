<template>
  <div>
    <h1>TEST 4</h1>
    <TodoInput :todoItem="todoText" @inputs="updateTodo" @adds="addTodo"></TodoInput>
  </div>
</template>

<script lang="ts">
  import Vue from "vue"
  import TodoInput from "@/components/TodoInput.vue";

  export default Vue.extend({
    components: {TodoInput},
    methods: {
      updateTodo(value: string) {
        this.todoText = value;
      },
      addTodo() {
        const value = this.todoText;
        localStorage.setItem(value, value);
        this.initTodoText();
      },
      initTodoText() {
        this.todoText = '';
      }
    },
    data() {
      return {
        todoText: ""
      }
    }
  })

</script>

<style scoped>

</style>