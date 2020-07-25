<template>
  <div class="todo-list">
    <h1>TodoList</h1>
    <div>
      <TodoItem v-for="item of list" v-bind:key="item.id" v-bind:item="item" v-on:del-item="deleteItem" />
    </div>
  </div>
</template>

<script>
  import TodoItem from "./TodoItem";

  export default {
    name: "TodoList",
    components: {
      TodoItem,
    },
    data() {
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
            title: "Make Awesome App with Vue",
            isCompleted: false,
          },
        ],
      };
    },
    methods: {
      deleteItem(id) {
        this.list = this.list.filter((v) => v.id !== id);
      },
    },
  };
</script>

<style lang="scss" scoped>
  .todo-list {
    width: 100%;
    max-width: 500px;
    padding: 64px 32px;
    margin: 0 auto;

    h1 {
      text-align: center;
      margin-bottom: 16px;
    }

    div {
      width: 100%;
    }
  }
</style>
