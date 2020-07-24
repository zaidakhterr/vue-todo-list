<template>
  <div>
<li  v-bind:class="{ completed: item.isCompleted }">{{ item.title }}</li>
  </div>
</template>

<script>
export default {
  name:"TodoList",
  props:{
    item: Object
  }
}
</script>

<style scoped>
  .completed {
    text-decoration: line-through;
  }
</style>
