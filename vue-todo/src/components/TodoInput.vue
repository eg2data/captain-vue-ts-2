<template>
  <div>
    <label for="todo-item">오늘 할 일: </label>
    <input id="todo-item" type="text" @input="handleInput" :value="todoItem">
    <button type="button" @click="addTodo">추가</button>
  </div>
</template>

<script lang="ts">
import Vue from "vue"

export default Vue.extend({
  // props: ["todoItem"],
  props: {
    "todoItem": {
      type: String,
      required: true
    }
  },
  methods: {
    addTodo() {
      this.$emit("adds")
    },
    handleInput(event: InputEvent) {
      const eventTarget = event.target as HTMLInputElement
      this.$emit("inputs", eventTarget.value)

    }
  }

})

</script>

<style scoped>

</style>