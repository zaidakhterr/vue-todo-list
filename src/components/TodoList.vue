<template>
  <div>
    <h1>TodoList</h1>
    <ul>
      <TodoItem v-for="item of list" v-bind:key="item.id" v-bind:item="item" />
    </ul>
  </div>
</template>

<script>
  import TodoItem from "./TodoItem";

  export default {
    name: "TodoList",
    components: {
      TodoItem,
    },
    data: function() {
      return {
        list: [
          {
            id: 1,
            title: "Install Vue CLI",
            isCompleted: true,
          },
          {
            id: 2,
            title: "Create Vue Project",
            isCompleted: true,
          },
          {
            id: 3,
            title: "Make TodoList App with Vue",
            isCompleted: false,
          },
        ],
      };
    },
  };
</script>
