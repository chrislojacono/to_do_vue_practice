<template>
<div class="body-item">
  <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
    <p class="todo-text">
      <input type="checkbox" v-on:change="markComplete" :checked="todo.completed">
      {{todo.title}}
      <button @click="$emit('del-todo', todo.id)" class="del">X</button>
      </p>  
  </div>
</div>
</template>

<script>


export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete(){
      this.todo.completed = !this.todo.completed
    },
  }
}
</script>

<style scoped>
  .todo-item {
    padding: 10px;
    border-radius: 3rem;
    margin: 2px;
    /* background: hsl(204 100% 5%); */
    min-block-size: 100%;
    min-inline-size: 100%;
    box-sizing: border-box;
    display: grid;
    background: linear-gradient(
      to left, 
      hsl(203, 25%, 63%), 
      hsl(204, 100%, 87%)
    );

    font-family: system-ui;
    font-size: min(200%, 5vmin);
  }

  h1 {
    font-size: 10vmin;
    line-height: 1.1;
  }

  p {
    font-family: "Dank Mono", ui-monospace, monospace;
  }

  .todo-text {
    font-family: 'Poppins', sans-serif;
    margin: 5px;
    color: black;

  }
  input{
    margin: 0 10px;
  }

  .is-complete {
    text-decoration: line-through;
  }

  .del {
    background-color: red;
    border: none;
    padding: 5px 9px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
    margin-top: 9px;
  }
</style>
