<template>
  <div>
    <nav-bar></nav-bar>
    <todo v-if="postType === 'todos'" :type="postType"></todo>
    <dummy-data v-if="postType === 'posts'"></dummy-data>
  </div>
</template>

<script>
import { bus } from "@/main";
import NavBar from "./components/Navbar";
import Todo from "./components/Todo";
import DummyData from "./components/DummyData";

export default {
  name: "App",
  components: {
    NavBar,
    Todo,
    DummyData,
  },
  data: () => ({
    postType: "todos",
  }),

  created() {
    bus.$on("post-type-selected", (data) => {
      this.postType = data;
    });
  },

  methods: {
    selectPost(postType) {
      this.postType = postType;
    },
  },
};
</script>
@import
url('https://fonts.googleapis.com/css2?family=Montserrat:wght@500&display=swap');
<style>
* {
  padding: 0;
  font-family: "Montserrat", sans-serif;
}
</style>
