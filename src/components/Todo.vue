<template>
  <div>
    <todo-form v-on:add-todo="addTodo"></todo-form>
    <table-list
      :dataList="todos"
      :columns="columns"
      :properties="properties"
      :type="type"
      v-on:del-todo="deleteTodo"
    ></table-list>
  </div>
</template>

<script>
import TodoForm from "./TodoForm";
import TableList from "./TableList";

export default {
  components: {
    TodoForm,
    TableList,
  },
  props: ["type"],
  data: () => ({
    columns: ["Name", "Status", "Functions"],
    properties: ["title", "completed"],
    todos: [],
  }),
  methods: {
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo];
    },
    deleteTodo(id) {
      let todos = localStorage.getItem("todos");
      this.todos = JSON.parse(todos);
      this.todos = this.todos.filter((todo) => todo.id !== id);
      localStorage.setItem("todos", JSON.stringify(this.todos));
    },
  },
  created() {
    let todos = localStorage.getItem("todos");
    if (todos) {
      this.todos = JSON.parse(todos);
    }
  },
};
</script>

<style></style>
