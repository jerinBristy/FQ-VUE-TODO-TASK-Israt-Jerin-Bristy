<template>
  <div>
    <ul>
      <li>
        <a class="active" href="#" @click.prevent="navbarType('todos')"
          >Todos</a
        >
      </li>
      <li><a @click.prevent="navbarType('posts')">Posts</a></li>
    </ul>
  </div>
</template>

<script>
import { bus } from "@/main";

export default {
  methods: {
    navbarType(data) {
      bus.$emit("post-type-selected", data);
    },
  },
};
</script>

<style>
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background-color: #333;
}

li {
  float: left;
}

li a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

li a:hover {
  background-color: #111;
}
</style>
