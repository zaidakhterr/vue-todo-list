<template>
  <div id="app">
    <HelloWorld msg="Hello World" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
  },
};
</script>

<style>
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
}
</style>
