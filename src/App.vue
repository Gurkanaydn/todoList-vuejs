<script>
import todoList from './components/TodoList.vue';

export default {
  components: {
    todoList,
  },
  data(){
    return{
    }
  }
};
</script>

<template>
  <div>
    <todoList></todoList>
  </div>
</template>

<!-- <style>
.h1{
    font-family: 'Courier New', Courier, monospace;
  background-color: #b3cccc;
  margin: auto;
  width: 50%;
  border: 2px solid black;
  padding: 10px;
}
</style> -->