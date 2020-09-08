<template>
  <table-list
    :dataList="posts"
    :columns="columns"
    :properties="properties"
  ></table-list>
</template>

<script>
import TableList from "./TableList";

export default {
  components: {
    TableList,
  },

  data: () => ({
    columns: ["Title", "Description", "Author"],
    properties: ["title", "description", "author"],
    posts: [
      {
        title: "Post One",
        description:
          "  Lorem ipsum, dolor sit amet consectetur adipisicing elit. In veniam et eius accusamus soluta asperiores iste explicabo repellat quis ex eos, perferendis est sed similique fuga tempora optio doloremque il.",
        author: "Chandler Bing",
      },
      {
        title: "Post Two",
        description:
          "  Lorem ipsum, dolor sit amet consectetur adipisicing elit. In veniam et eius accusamus soluta asperiores iste explicabo repellat quis ex eos, perferendis est sed similique fuga tempora optio doloremque il.",
        author: "Monica Geller",
      },
      {
        title: "Post Three",
        description:
          "  Lorem ipsum, dolor sit amet consectetur adipisicing elit. In veniam et eius accusamus soluta asperiores iste explicabo repellat quis ex eos, perferendis est sed similique fuga tempora optio doloremque il.",
        author: "Joey Tribbiani",
      },
      {
        title: "Post Four",
        description:
          "  Lorem ipsum, dolor sit amet consectetur adipisicing elit. In veniam et eius accusamus soluta asperiores iste explicabo repellat quis ex eos, perferendis est sed similique fuga tempora optio doloremque il.",
        author: "Phoebe Buffay",
      },
      {
        title: "Post Five",
        description:
          "  Lorem ipsum, dolor sit amet consectetur adipisicing elit. In veniam et eius accusamus soluta asperiores iste explicabo repellat quis ex eos, perferendis est sed similique fuga tempora optio doloremque il.",
        author: "Ross Geller",
      },
      {
        title: "Post Six",
        description:
          "  Lorem ipsum, dolor sit amet consectetur adipisicing elit. In veniam et eius accusamus soluta asperiores iste explicabo repellat quis ex eos, perferendis est sed similique fuga tempora optio doloremque il.",
        author: "Rachel Green",
      },
    ],
  }),
};
</script>

<style></style>
