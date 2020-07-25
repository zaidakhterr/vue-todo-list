<template>
  <div id="app">
    <TodoList />
  </div>
</template>

<script>
  import TodoList from "./components/TodoList.vue";

  export default {
    name: "App",
    components: {
      TodoList,
    },
  };
</script>

<style lang="scss">
  *,
  *::before,
  *::after {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: "Montserrat", sans-serif;
    border-radius: 0;
  }

  body {
    width: 100%;
    overflow-x: hidden;
    min-height: 100%;
    background: #f5f5fa;
  }
</style>
