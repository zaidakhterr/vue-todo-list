<template>
  <div class="todo-list">
    <h1>TodoList</h1>
    <AddTodoForm v-on:add-item="addItem" />
    <transition-group name="list" tag="div">
      <TodoItem v-for="item of list" v-bind:key="item.id" v-bind:item="item" v-on:del-item="deleteItem" />
    </transition-group>
  </div>
</template>

<script>
  import TodoItem from "./TodoItem";
  import AddTodoForm from "./AddTodoForm";
  import { v4 as uuid } from "uuid";

  export default {
    name: "TodoList",
    components: {
      TodoItem,
      AddTodoForm,
    },
    data() {
      return {
        list: [
          {
            id: uuid(),
            title: "Install Vue CLI",
            isCompleted: true,
          },
          {
            id: uuid(),
            title: "Create Vue Project",
            isCompleted: true,
          },
          {
            id: uuid(),
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
      addItem(title) {
        console.log("title", title, title.length);
        if (title.length !== 0) {
          const newTodo = {
            id: uuid(),
            title,
            isCompleted: false,
          };
          this.list = [...this.list, newTodo];
        }
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
