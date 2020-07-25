<template>
  <div class="todo-list">
    <h1>TodoList</h1>
    <transition-group name="list" tag="div">
      <TodoItem v-for="item of list" v-bind:key="item.id" v-bind:item="item" v-on:del-item="deleteItem" />
    </transition-group>
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
    margin: 64px auto;

    h1 {
      text-align: center;
      margin-bottom: 16px;
    }

    > div {
      width: 100%;
      padding: 16px;
    }
  }

  .list-enter-active,
  .list-leave-active {
    transition: all 500ms;
  }

  .list-enter {
    opacity: 0;
    transform: translateX(-100%);
  }

  .list-leave-to {
    opacity: 0;
    transform: translateX(100%);
  }

  .list-leave-active {
    position: absolute;
  }
</style>
