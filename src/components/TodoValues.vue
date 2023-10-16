<script>
export default {
  props: ['valuefromInput'],
  methods:{
    deleteTodo(id){
        this.$emit('delete-todo',id)
    }
  }
}
</script>

<template>
  <div class="container">
    <h1 class="todos">Todos</h1>
    <div class="containter-div">
    
    <div v-if="!valuefromInput.length">
    <h1 class="notfound"> No Todos Found</h1>
    </div>  

    <div v-else v-for="todo in valuefromInput" >
        <div key="todo.id" class="container-items">
        <h1 >{{todo.value}}</h1>
        <div class="container-buttons">
          <!-- <button style="color: white; background-color: green; padding:5px 10px; margin: 0 10px; @click">Edit</button> -->
          <button style="background-color: red; color: white;padding: 5px 8px; margin: 0 10px;" @click="deleteTodo(todo.id)">Delete</button>
        </div>
    </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.todos{
    text-align: center;
    font-weight: 800;
    color: green;
}

.notfound{
    padding: 40px 0;
    text-align: center;
    font-size: large;
    font-weight: bold;
    color: white;
}

.containter-div {
  width: 100%;
  /* border: 2px solid green; */
  text-align: center;
}

.container-items {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  margin: 16px 0 ;
  padding: 0 10px;
  border-bottom: 2px white solid;
}

.container-buttons {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-evenly;
}

.container-buttons h1 {
  padding-left: 10px;
  color: white;
}
</style>
