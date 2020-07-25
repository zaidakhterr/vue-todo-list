<template>
  <div class="todo-item">
    <p v-bind:class="{ 'is-completed': item.isCompleted }" @click="toggleComplete">{{ item.title }}</p>
    <button class="del-btn" @click="deleteItem">&#x2716;</button>
  </div>
</template>

<script>
  export default {
    name: "TodoList",
    props: {
      item: Object,
    },
    methods: {
      toggleComplete() {
        this.item.isCompleted = !this.item.isCompleted;
      },
      deleteItem() {
        this.$emit("del-item", this.item.id);
      },
    },
  };
</script>

<style lang="scss" scoped>
  .todo-item {
    width: 100%;
    border: solid 1px #d9d9d9;
    background-color: #fff;
    border-radius: 3px;
    margin-bottom: 16px;
    padding: 8px 16px;
    display: flex;
    align-items: center;
    justify-content: space-between;

    p {
      position: relative;
      cursor: pointer;
      user-select: none;
      font-size: 1.2rem;

      &::after {
        position: absolute;
        content: "";
        height: 2px;
        width: 0px;
        background: rgba(#000, 0.5);
        transition: all 200ms;
        bottom: 10px;
        left: -5px;
      }
    }

    .is-completed::after {
      width: calc(100% + 10px);
    }

    .del-btn {
      cursor: pointer;
      height: 24px;
      width: 24px;
      line-height: 0px;
      text-align: center;
      color: #fff;
      background-color: rgb(224, 69, 69);
      border-radius: 50%;
      border: 1px solid transparent;
      transition: all 200ms;
      outline: none;

      &:hover {
        border-color: #000;
      }
    }
  }
</style>
