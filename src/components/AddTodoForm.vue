<template>
  <form>
    <input type="text" >
    <button type="submit" placeholder="Add todo...">Add Item</button>
  </form>
</template>

<script>
  export default {
    name:"AddTodoForm"
  }
</script>

<style lang="scss" scoped>
form{
  padding: 0 16px;
  display: flex;

  input{
    font-size: 1.1rem;
    outline: none;
    border-radius: 3px;
    border: 1px solid #d9d9d9;
    padding: 8px 16px;
    line-height: 0px;
    flex: 1;
    margin-right: 8px;
  }

  button{
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