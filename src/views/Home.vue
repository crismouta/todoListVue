<template>
  <div class="home" >
      <div id="main-container">
        <div class="title">
          <h1>Todo List</h1>
        </div>
        <div class="todolist">
          <TodoList />
        </div>
      </div>
  </div>
</template>

<script>

import TodoList from '../components/TodoList.vue'


export default {
  name: 'Home',
  
  components: {
    TodoList,
  }

}
</script>

<style>

  *{
      margin: 0;
      padding: 0;
      box-sizing: border-box;
  }

  body{
      font: bold 2rem 'Open Sans', sans-serif;
  }

  #main-container{
    width: 600px;
    margin: 100px auto;
    
  }

  .title{
    border: solid 2px #ccc;
    background-color: rgba(238, 238, 238, 0.993);
  
  }

  .todolist{
    border: solid 2px #ccc;
  }


</style>
