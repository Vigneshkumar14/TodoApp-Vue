<script>
import TodoInput from '../components/TodoInput.vue'
import TodoValues from '../components/TodoValues.vue'

export default {
  components: { TodoInput, TodoValues },
  data() {
    return {
      valuefromInput: [{id:1,value: "Welcome to Todos"}, {id:2, value:"Add todos to effectively manage your tasks"}]
    }
  },
  methods: {
    getValue(value) {
      this.valuefromInput.push({ id: this.valuefromInput.length + 1, value })
    },
    deleteTodo(id) {
      const updatedValue = this.valuefromInput.filter((todo) => todo.id !== id)
      this.valuefromInput = updatedValue
    },
    editTodo(id,value){
      const editObj = this.valuefromInput.find((todo)=> todo.id === id);
      editObj.value  = value;
    }
  }
}
</script>

<template>
  <main>
    <TodoInput @input-value="getValue" />
    <h1>{{ valuefromInput }}</h1>
    <p style="text-align: center;">Above view is to see how todos are stored</p>
    <div class="spaces">
      <TodoValues :valuefromInput="valuefromInput" @delete-todo="deleteTodo" @edit-todo="editTodo" />
    </div>
  </main>
</template>

<style scoped>
.spaces {
  margin: 40px 0;
}
</style>
