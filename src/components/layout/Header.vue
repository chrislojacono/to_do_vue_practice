<template>
  <header class="header">
    <h1>To-do List</h1>
  </header>  
</template>

<script>
export default {
  name: "Header"
}
</script>

<style scoped>
  .header {
    background: rgb(6, 97, 104);
    color: #fff;
    text-align: center;
    padding: 10px;
    border-radius: 20px;
    margin: 5px;
  }

  .header a {
    color: #fff;
    padding-right: 5px;
  }
</style>