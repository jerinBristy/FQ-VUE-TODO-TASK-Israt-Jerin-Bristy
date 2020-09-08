<template>
  <div>
    <form @submit.prevent="addTodo">
      <label for="todo">Enter Todo</label>
      <input type="text" v-model="title" placeholder="Enter Todo" id="todo" />

      <input type="submit" class="button" value="Add Todo" />
    </form>
  </div>
</template>

<script>
import { v4 as uuidv4 } from "uuid";

export default {
  components: {},
  data: () => ({
    title: "",
  }),
  methods: {
    addTodo() {
      const newTodo = {
        id: uuidv4(),
        title: this.title,
        completed: false,
      };
      // Send up to parent
      this.title = "";
      let todos = localStorage.getItem("todos");
      todos = JSON.parse(todos);
      if (!todos) {
        todos = [newTodo];
      } else {
        todos.push(newTodo);
      }
      localStorage.setItem("todos", JSON.stringify(todos));
      this.$emit("add-todo", newTodo);
    },
  },
};
</script>

<style>
input[type="text"],
select {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}

input[type="submit"] {
  width: 100%;
  background-color: #4caf50;
  color: white;
  padding: 14px 20px;
  margin: 8px 0;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

input[type="submit"]:hover {
  background-color: #45a049;
}

div {
  border-radius: 5px;
  background-color: #f2f2f2;
  padding: 20px;
}
</style>
