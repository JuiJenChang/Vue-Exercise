<template>
  <div>
    <h1>My todo list</h1>
    <input v-model="newItem" v-on:keyup.13="addTodo" />
    <ul>
      <li v-for="(todo, index) in todos" :key="index">
          {{todo}}
        <button v-on:click="removeTodo(index)">刪除</button>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "TodoList",
  data() {
    return {
      todos: [],
      newItem: "",
    };
  },
  methods: {
    addTodo() {
      if (this.newItem !== "") {
        this.todos.push(this.newItem);
      }
    },
    removeTodo(index) {
      this.todos = this.todos.filter((todo, i) => i !== index);
    }
  }
};
</script>

<style>
input {
    outline: none;
}
ul {
  list-style-type: none;
  padding: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
}
li {
    min-width: 500px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}
button {
    border: 0;
    border-radius: 99rem;
    background: #40bdee;
    color: #ffffff;
    outline: none;
    cursor: pointer;
}
</style>
