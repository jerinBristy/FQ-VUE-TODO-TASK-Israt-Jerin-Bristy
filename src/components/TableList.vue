<template>
  <table>
    <tr>
      <th v-for="(column, i) in columns" :key="i">{{ column }}</th>
    </tr>
    <tr v-for="(data, i) in dataList" :key="i">
      <td v-for="(property, j) in properties" :key="j">{{ data[property] }}</td>
      <td v-if="type === 'todos'">
        <input type="checkbox" v-on:change="markComplete(data.id)" />
        <button @click="$emit('del-todo', data.id)" class="del">
          x
        </button>
      </td>
    </tr>
  </table>
</template>

<script>
export default {
  props: ["dataList", "columns", "properties", "type"],
  methods: {
    markComplete(id) {
      //    this.todo.completed= !this.todo.completed;
      this.dataList.forEach((data) => {
        if (data.id == id) {
          data.completed = !data.completed;
        }
      });
    },
  },
};
</script>

<style>
input[type="checkbox"] {
  margin: 10px;
}
.del {
  background-color: red; /* Green */
  border: none;
  color: white;
  padding: 5px 10px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
}

* {
  max-width: 800px;
  margin: auto;
}
table {
  border-collapse: collapse;
  width: 100%;
}

th,
td {
  padding: 8px;
  text-align: left;
  border-bottom: 1px solid #ddd;
}

tr:hover {
  background-color: #f5f5f5;
}
</style>
