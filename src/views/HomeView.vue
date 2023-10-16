<script>
import TodoInput from '../components/TodoInput.vue'
import TodoValues from '../components/TodoValues.vue'

export default {
  components: { TodoInput, TodoValues },
  data() {
    return {
      valuefromInput: []
    }
  },
  methods: {
    getValue(value) {
      this.valuefromInput.push({ id: this.valuefromInput.length + 1, value })
    },
    deleteTodo(id) {
      const updatedValue = this.valuefromInput.filter((todo) => todo.id !== id)
      this.valuefromInput = updatedValue
    }
  }
}
</script>

<template>
  <main>
    <TodoInput @input-value="getValue" />
    <h1>{{ valuefromInput }}</h1>
    <div class="spaces">
      <TodoValues :valuefromInput="valuefromInput" @delete-todo="deleteTodo" />
    </div>
  </main>
</template>

<style scoped>
.spaces {
  margin: 40px 0;
}
</style>
