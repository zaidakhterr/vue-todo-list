<template>
  <form @submit="addItem">
    <input type="text" autocomplete="off" name="title" v-model.trim="title" />
    <button type="submit">Add Item</button>
  </form>
</template>

<script>
  export default {
    name: "AddTodoForm",
    data() {
      return {
        title: "",
      };
    },
    methods: {
      addItem(e) {
        e.preventDefault();
        this.$emit("add-item", this.title);
        this.title = "";
      },
    },
  };
</script>

<style lang="scss" scoped>
  form {
    padding: 16px;
    display: flex;

    input {
      font-size: 1.1rem;
      outline: none;
      border-radius: 3px;
      border: 1px solid #d9d9d9;
      padding: 8px 16px;
      line-height: 0px;
      flex: 1;
      margin-right: 8px;
    }

    button {
      cursor: pointer;
      outline: none;
      color: #fff;
      background: rgb(10, 185, 89);
      border: 1px solid #d9d9d9;
      padding: 8px;
      border-radius: 3px;
    }
  }
</style>
