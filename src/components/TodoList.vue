<template>
  <div>
    <h1>TodoList</h1>
    <ul>
      <li v-for="item in list" v-bind:key="item.id">{{ item.task }}</li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: "TodoList",
    data: function() {
      return {
        list: [
          {
            id: 1,
            task: "Install Vue CLI",
            isCompleted: true,
          },
          {
            id: 2,
            task: "Create Vue Project",
            isCompleted: true,
          },
          {
            id: 3,
            task: "Make TodoList App",
            isCompleted: false,
          },
        ],
      };
    },
  };
</script>

<style scoped></style>
