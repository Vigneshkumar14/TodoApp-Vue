<script>
export default {
  data() {
    return {
      inputValue: ''
    }
  },
  methods: {
    emitInput() {
      this.$emit('input-value', this.inputValue)
      this.inputValue = ''
    }
  }
}
</script>

<template>
  <div class="greetings">
    <h1 class="green">Enter the Todo Below</h1>

    <input class="center" type="text" v-model="inputValue" placeholder="Type here to Add Todo" />

    <button class="green-button" @click="emitInput">Add Todo</button>
  </div>
</template>

<style scoped>
.greetings {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.green {
  text-align: center;
  width: 100%;
  color: green;
  font-weight: bolder;
  display: block;
}

.center {
  align-items: center;
  justify-content: center;
  width: 70%;
  /* margin: 20px 20px 0 0; */
  padding: 10px;
  background-color: transparent;
  color: white;
  border: 2px solid green;
}

.green-button {
  margin: 15px 0;
  border: 2px white solid;
  background-color: green;
  padding: 10px 25px;
  color: white;
  font-weight: bold;
  font-size: larger;
  text-align: center;
}
</style>
